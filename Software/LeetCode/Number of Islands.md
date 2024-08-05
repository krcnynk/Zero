Given function declaration
```int numIslands(char** grid, int gridSize, int* gridColSize) {}```

Use BFS (or DFS) and queue

	don't know the amount of memory needed during compile time so malloc and calloc

## Okay Way
```c
#include <stdio.h>
#include <stdlib.h>
bool isValid(int i, int lim)

{

    if (i >= 0 && i < lim)
        return true;
    return false;

}
void dfs(int row, int col, int gridSize, int* gridColSize,  char** grid)

{
    grid[row][col] = '0';
    if(isValid(row-1,gridSize) && grid[row-1][col] != '0')
        dfs(row-1,col,gridSize, gridColSize, grid);
    if(isValid(row+1,gridSize) && grid[row+1][col] != '0')
        dfs(row+1,col,gridSize, gridColSize, grid);
    if(isValid(col-1,*gridColSize) && grid[row][col-1] != '0')
        dfs(row,col-1,gridSize, gridColSize, grid);
    if(isValid(col+1,*gridColSize) && grid[row][col+1] != '0')
        dfs(row,col+1,gridSize, gridColSize, grid);
}

  

int numIslands(char** grid, int gridSize, int* gridColSize) {
    int numIslands = 0;
    for (int i = 0; i < gridSize; ++i) {
        for (int j = 0; j < gridColSize[i]; ++j) {
            if (grid[i][j] == '1') {
                numIslands++;
                dfs(i, j, gridSize, gridColSize, grid);
            }
        }
    }
    return numIslands;
}
```

```python
class Solution:
    def isValid(self, i, max):
        return 0 <= i < max

    def dfs(self, r, c, grid: List[List[str]]):
        grid[r][c] = '0'
        rowMax, colMax = len(grid), len(grid[0])
        if self.isValid(r-1, rowMax) and grid[r-1][c] == '1':
            self.dfs(r-1, c, grid)
        if self.isValid(r+1, rowMax) and grid[r+1][c] == '1':
            self.dfs(r+1, c, grid)
        if self.isValid(c-1, colMax) and grid[r][c-1] == '1':
            self.dfs(r, c-1, grid)
        if self.isValid(c+1, colMax) and grid[r][c+1] == '1':
            self.dfs(r, c+1, grid)

    def numIslands(self, grid: List[List[str]]) -> int:
        numIsland = 0
        for r, row in enumerate(grid):
            for c, col in enumerate(row):
                if grid[r][c] == '1':
                    numIsland += 1
                    self.dfs(r, c, grid)
        return numIsland

```


## Bad Way
```c
#include <stdio.h>
#include <stdlib.h>

void bfs(int row, int col, int gridSize, int* gridColSize, int** vis, char** grid) {
    int queueSize = gridSize * (*gridColSize);
    int* queue = (int*)malloc(queueSize * 2 * sizeof(int));
    if (queue == NULL) return;
    int front = 0, rear = 0;
    queue[rear++] = row;
    queue[rear++] = col;
    vis[row][col] = 1;

    while (front < rear) {
        row = queue[front++];
        col = queue[front++];
        int left = col - 1, right = col + 1, up = row - 1, down = row + 1;
        if (left >= 0 && left < *gridColSize && grid[row][left] == '1' && vis[row][left] == 0) {
            vis[row][left] = 1;
            queue[rear++] = row;
            queue[rear++] = left;
        }
        if (right >= 0 && right < *gridColSize && grid[row][right] == '1' && vis[row][right] == 0) {
            vis[row][right] = 1;
            queue[rear++] = row;
            queue[rear++] = right;
        }
        if (up >= 0 && up < gridSize && grid[up][col] == '1' && vis[up][col] == 0) {
            vis[up][col] = 1;
            queue[rear++] = up;
            queue[rear++] = col;
        }
        if (down >= 0 && down < gridSize && grid[down][col] == '1' && vis[down][col] == 0) {
            vis[down][col] = 1;
            queue[rear++] = down;
            queue[rear++] = col;
        }
    }
    free(queue);
}

int numIslands(char** grid, int gridSize, int* gridColSize) {
    int** vis = (int**)malloc(gridSize * sizeof(int*));
    if (vis == NULL) return 1;
    for (int i = 0; i < gridSize; i++) {
        vis[i] = (int*)calloc(*gridColSize, sizeof(int));
        if (vis[i] == NULL) {
            for (int j = 0; j < i; j++) free(vis[j]);
            free(vis);
            return 1;
        }
    }
    int numIslands = 0;
    for (int i = 0; i < gridSize; ++i) {
        for (int j = 0; j < gridColSize[i]; ++j) {
            if (grid[i][j] == '1' && vis[i][j] == 0) {
                numIslands++;
                bfs(i, j, gridSize, gridColSize, vis, grid);
            }
        }
    }
    for (int i = 0; i < gridSize; i++) free(vis[i]);
    free(vis);
    return numIslands;
}

```