Tags: [[C]]

```
struct tag
{
	char lname[20];
	float rate;
};
```

This struct can get really big, you dont want to pass whole struct into a function. This will waste stack, passing a pointer will use minimal amount of stack.

```
struct tag *st_ptr;
st_ptr = &my_struct;
(*st_ptr).age = 63; // or use st_ptr->age = 63;
```