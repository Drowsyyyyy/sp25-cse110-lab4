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

**Return value:** [50, 100, 150]
Explanation:
The function loops over each element in prices (100, 200, 300).
For each price it computes discountedPrice = price * (1 - discount)
so with discount = 0.5 you get 50, 100, and 150.
It then rounds to two decimal places via Math.round(discountedPrice * 100) / 100
Each rounded value is pushed into the discounted array, which is finally returned.
No errors occur because all variables are declared with var (function-scoped), so the loop and rounding logic execute correctly.

### 5. What happens at line 12 and why?

At line 12, the statement console.log(i) will throw a ReferenceError: i is not defined. This is because:

The loop counter i is declared with let in the for loop header.

Variables declared with let are block-scoped, so i only exists within the { … } of the for loop.

Once the loop finishes, i goes out of scope and cannot be accessed from line 12.

### 6. What will happen at line 13 and why? If the code causes an error, explain why.

At line 13 you’ll get a ReferenceError saying that discountedPrice is not defined. That happens because discountedPrice was declared with let inside the for-loop block, so it only exists within that block and can’t be accessed afterward.

### 7. What will happen at line 14 and why? If the code causes an error, explain why.

At line 14 you’ll see the value of finalPrice logged (in this case 150). There’s no error because finalPrice was declared with let in the outer function scope, so it’s still in scope after the loop and holds the last computed discounted price.

### 8. What will this function return? Give a brief explanation. If the code causes an error, explain why.

It will return the array [50, 100, 150]. On each loop iteration it computes prices[i] × (1 – discount), rounds that to two decimal places, pushes it into the discounted array, and after processing all three inputs the function returns that array. There’s no error, since any console.log of block-scoped variables has been commented out.

### 9. What will happen at line 11 and why? If the code causes an error, explain why. 

At line 11 you’ll get a ReferenceError (“i is not defined”). That’s because i was declared with let in the for loop header, so its scope is limited to the loop block and it doesn’t exist afterward.

### 10. What will happen at line 12 and why? If the code causes an error, explain why. 

It will print 3 to the console—since you stored prices.length in the const length variable at the top of the function, length is still in scope there, so logging it simply outputs the array’s length. No error occurs.

### 11. What will this function return? Give a brief explanation. If the code causes an error, explain why. 

It returns the array [50, 100, 150]. The function creates an empty discounted array, then loops over each price, computes price × (1 – discount) for each element, pushes that value into discounted, and finally returns that array. No errors occur because all variables logged inside comments are either in scope or never accessed.

 ### 12. Given the above Object, write the notation for: 
A.Accessing the value of the name property in the student object
B.Accessing the value of the Grad Year property in the student object
C.Calling the function for the greeting property in the student object
D.Accessing the name property of the object in the Favorite Teacher property in student
E.Access index zero in the array of the courseLoad property of the student object

A. student.name
B. student['Grad Year']
C. student.greeting()
D. student['Favorite Teacher'].name
E. student.courseLoad[0]

### 13. Arithmetic
A. ‘3’ + 2 → “32”
because string + value concatenates and 2 is coerced to “2”.
B. ‘3’ - 2 → 1
because the – operator forces numeric conversion, “3”→3, so 3–2=1.
C. 3 + null → 3
null is coerced to 0, so 3+0=3.
D. ‘3’ + null → “3null”
with a string performs concatenation, null→“null”.
E. true + 3 → 4
true→1, so 1+3=4.
F. false + null → 0
false→0 and null→0, so 0+0=0.
G. ‘3’ + undefined → “3undefined”
with a string concatenates the string form of undefined.
H. ‘3’ - undefined → NaN
undefined coerces to NaN under subtraction, so the result is NaN.

### 14.Comparison
A. '2' > 1 → true
'2'→2 then 2>1.
B. '2' < '12' → false
when both operands are strings, they’re compared lexicographically: “2” > “1…”.
C. 2 == '2' → true
loose equality coerces '2'→2, so 2==2.
D. 2 === '2' → false
strict equality checks type too; number ≠ string.
E. true == 2 → false
true→1, so 1==2 is false.
F. true === Boolean(2) → true
Boolean(2) is true, so true===true.

### 15. The == operator performs type coercion before comparing (e.g. '2'==2 is true), whereas === requires both value and type to match exactly (so '2'===2 is false).
