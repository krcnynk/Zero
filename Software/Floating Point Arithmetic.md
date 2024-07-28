sign1-exponent8-mantissa32 
(−1)S∗ 1.M ∗ 2(E−127)
- exponent is a window [1,2] or [2,4] or [4,8]
- offset divides window into bucket

In the window [2048,4096] the 8388608 offset precision $\frac{4096-2048}{8388608}=0.0002$

![[../floating_point_window.svg]]
https://fabiensanglard.net/floating_point_visually_explained/ very good source


Convert 3.55123 to Binary
- Integer part
	- divide by 2 and record remainders till quotient of 0
- Convert fractional part
	- multiply fraction by 2 and record integer part until desired precision or fraction becomes 0
- So we get 11.100011110011 = 1.1100011110011 × 2^1
	- sign 0 , exponent 10000000, mantissa 11000111100110000000000
TO BE READ!

```c
void floatToIEEE754(float value, uint32_t *sign, uint32_t *exponent, uint32_t *mantissa) { 
uint32_t *p = (uint32_t *)&value; 
// Extract IEEE 754 components 
*sign = (*p >> 31) & 0x1; 
*exponent = (*p >> 23) & 0xFF; 
*mantissa = *p & 0x7FFFFF; }
```
https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html long source

https://en.wikipedia.org/wiki/Floating-point_unit Hardware/Software