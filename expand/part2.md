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

### 3. What will happen at line 14 and why? If the code causes an error, explain why.

At line 14, you log the variable finalPrice outside the for loop. Since finalPrice was declared with var at the top of the function

it is function-scoped and thus accessible anywhere inside discountPrices, including after the loop.

Therefore:
No error will occur.

It will print the last value assigned to finalPrice during the final iteration of the loop.

For discountPrices([100, 200, 300], 0.5):

Iteration 0 → finalPrice = 50

Iteration 1 → finalPrice = 100

Iteration 2 → finalPrice = 150

After loop, console.log(finalPrice); logs: 150

### 4. What will this function return? Give a brief explanation why. If the code causes an error, explain why.

**Return value:**
```js
[50, 100, 150]

Explanation:

The function loops over each element in prices (100, 200, 300).

For each price it computes discountedPrice = price * (1 - discount)

so with discount = 0.5 you get 50, 100, and 150.

It then rounds to two decimal places via Math.round(discountedPrice * 100) / 100

Each rounded value is pushed into the discounted array, which is finally returned.

No errors occur because all variables are declared with var (function-scoped), so the loop and rounding logic execute correctly.

### 5. What happens at line 12 and why?

At line 12, the statement
```js
console.log(i)
