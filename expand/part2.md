### 1. What happens at line 12 and why?

Since i is declared with var, which is function-scoped, it is accessible anywhere in the entire discountPrices function, including after the loop.

Line 12 will not cause an error.

It will print the final value of i after the loop ends.

With input [100, 200, 300], the loop runs while i < 3, so after the last iteration:

i becomes 3

So console.log(i); logs: 3

### 2. What will happen at line 13 and why?

At line 13, the variable discountedPrice is logged outside the for loop where it was declared.

However, discountedPrice was declared using var inside the loop

In JavaScript, variables declared with var are function-scoped, not block-scoped. This means that discountedPrice is accessible anywhere within the entire discountPrices function, even outside the for loop.

Line 13 will not cause an error.

It will print the last value assigned to discountedPrice during the loop.

If the input is [100, 200, 300] and discount = 0.5:

Final loop iteration computes: 300 * 0.5 = 150

So discountedPrice = 150

console.log(discountedPrice); logs 150

^^^ 3. What will happen at line 14 and why? If the code causes an error, explain why. ^^^
