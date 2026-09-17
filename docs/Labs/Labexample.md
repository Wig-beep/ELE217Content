<!-- 3. The Toggle Script -->
<script>
function toggleDeepDive() {
  var checkBox = document.getElementById("deepDiveCheck");
  var content = document.getElementById("deepDiveSection");
  if (checkBox.checked == true) {
    content.style.display = "block";
  } else {
    content.style.display = "none";
  }
}
</script>

# Variables, Data Types, Libraries, Inputs and Output in C

## Information Example

Variables refers to the data that will be used by the code in various means. C needs explicitly informing what data type it is storing in each variable, to ensure it can carry out subsequent calculations.

| Data Type | Description | Example | Size |
| :---: | :--- | :--- | :---: |
| <code style="color: #005cc5; font-weight: bold;">int</code> | Signed integer (whole numbers) | `int radius = 6;` | 16 or 32 bits |
| <code style="color: #005cc5; font-weight: bold;">char</code> | Single ASCII character or 8-bit integer | `char status = 'A';` | 8 bits (1 byte) |
| <code style="color: #005cc5; font-weight: bold;">bool</code> | Boolean logic value (`true` or `false`)* | `bool is_ready = true;` | 8 bits (1 byte) |
| <code style="color: #005cc5; font-weight: bold;">float</code> | Single-precision floating-point number | `float voltage = 3.3f;` | 32 bits (4 bytes) |


## Copy Code Example

```c
#include <stdio.h>
#include <math.h>

int decimal = 42;
```
<!-- 2. The Hidden Content -->
<div id="deepDiveSection" markdown="1" style="display: none; border-left: 4px solid #d99100; padding-left: 15px; margin-top: 15px; background-color: #fafafa;">

### Deep Dive: What `#include <stdio.h>` Actually Does

At the start of the lab, we glossed over `#include <stdio.h>` as "the header file needed for `printf()`". Here is what is happening under the hood:

1. **Pre-processor Pass:** Before compilation begins, the C preprocessor (`cpp`) literally copy-pastes the entire contents of `stdio.h` into the top of your source file.
2. **Function Prototypes:** It tells the compiler the exact memory signature of `printf()` so it knows how many arguments and byte widths to expect on the call stack.
3. **Register/Peripheral Mapping:** In embedded C, header files perform this same trick to define hardware register addresses (e.g., `#define GPIOA_BASE (0x40020000UL)`).

</div>


## Questions

Convert the decimal number 42 to binary

<details>
  <summary><b>Answer: </b></summary>
  <br>
  <b>Answer:</b> <code>101010</code><br>
  <i>42 = 101010 = 
  1*0 + 2*1 + 4*0 + 8*1 + 16*0 + 32*1</i>
</details>

## Check answer snippet

<div style="background-color: #f8f9fa; border: 1px solid #e9ecef; border-radius: 8px; padding: 16px; margin: 1rem 0; max-width: 480px; font-family: system-ui, -apple-system, sans-serif;">
  <label for="binaryInput" style="display: block; font-weight: 600; margin-bottom: 8px; color: #212529;">
    Practice: Convert <code style="color: #005cc5;">0x3A</code> to decimal
  </label>
  
  <div style="display: flex; gap: 8px;">
    <input type="text" id="binaryInput" placeholder="binary result" 
           style="flex: 1; padding: 8px 12px; border: 1px solid #ced4da; border-radius: 4px; font-family: monospace; font-size: 14px;" />
    <button onclick="checkBinaryAnswer()" 
            style="padding: 8px 16px; background-color: #005cc5; color: white; border: none; border-radius: 4px; font-weight: 600; cursor: pointer;">
      Check
    </button>
  </div>

  <p id="feedbackMessage" style="margin-top: 10px; margin-bottom: 0; font-size: 14px; font-weight: bold;"></p>
</div>

<script>
function checkBinaryAnswer() {
  // Get input and strip spaces
  const userAns = document.getElementById('binaryInput').value.replace(/\s+/g, '');
  const feedback = document.getElementById('feedbackMessage');

  if (userAns === '58') {
    feedback.style.color = '#2e7d32';
    feedback.textContent = ' Correct! (0x3 = 48, 0xA = 10)';
  } else if (userAns === '') {
    feedback.style.color = '#d32f2f';
    feedback.textContent = 'Please enter an answer first.';
  } else {
    feedback.style.color = '#d32f2f';
    feedback.textContent = ' Incorrect. Try again! Hint: 3*16^(1) and 10*16^(0).';
  }
}
</script>


<div style="background-color: #f7e1b5; border: 2px solid #d99100; border-radius: 8px; padding: 15px; margin: 25px 0;">
  <label style="font-weight: bold; font-size: 1.05em; cursor: pointer; display: flex; align-items: center; gap: 10px;">
    <input type="checkbox" id="deepDiveCheck" onclick="toggleDeepDive()" style="width: 20px; height: 20px; cursor: pointer;">
    <span> "Worry About It Now" Button</span>
  </label>
</div>


