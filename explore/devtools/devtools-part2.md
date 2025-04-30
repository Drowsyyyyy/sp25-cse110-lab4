### 1. What was the bug?
Inputs retrieved by document.getElementById(...).value are strings, so num1 + num2 performed string concatenation instead of numeric addition (e.g. "2" + "3" → "23").

### 2. How would you fix it?
function calculateSum(num1, num2) {
  // convert string inputs to numbers
  let result = Number(num1) + Number(num2);
  return result;
}
