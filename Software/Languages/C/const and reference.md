Tags: [[C]]

- void function(const char* str)
pointer to constant char
data cannot be modified

- void function(char* const str) {
constant pointer to char
pointer cannot be changed but data can change

- void function(const char* const str)
constant pointer to constant char
pretty much read only everything

---

- void function(char*& ptr)
reference to pointer 
contents of original pointer may change (different address)

- void function(const char*& ptr)
reference to pointer that points to constant char
pointer can change, reassigned but data cannot change

- void function(char* const& ptr)
reference to constant pointer
pointer cannot move, but data can change

- void function(const char* const& str)
reference to const pointer that holds constant char
pointer cannot be changed, data cannot be changed, performance gain