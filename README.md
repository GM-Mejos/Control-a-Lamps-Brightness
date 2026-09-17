# Arduino Lamp Brightness Logic — Lab Submission


## 2. Completed Test Table

| Brightness setting | Switch state | Expected lamp brightness | Observed output |
| :--- | :--- | :--- | :--- |
| 0 | On | 0 | 0 |
| 50 | On | 50 | 50 |
| 100 | On | 100 | 100 |
| 0 | Off | 0 | 0 |
| 50 | Off | 0 | 0 |
| 100 | Off | 0 | 0 |

---

## 3. Explanation of Parameters & Return Value

* **Parameters (`bool switchOn, int brightnessSetting`)**: 
  - `switchOn`: A boolean parameter representing the status of the switch (`true` for ON, `false` for OFF).
  - `brightnessSetting`: An integer parameter representing the targeted brightness level (ranging from `0` to `100`).
* **Return Value (`int`)**: 
  - The function returns an integer representing the calculated lamp brightness. If `switchOn` is `true`, it returns the value passed into `brightnessSetting`. If `switchOn` is `false`, it returns `0` regardless of the setting.

---

## 4. Answers to Coding Check Questions

1. **In `int brightnessSetting = 75;`, identify the data type, variable name, and initial value. How would you change the value to 50?**
   * **Data type:** `int` (integer)
   * **Variable name:** `brightnessSetting`
   * **Initial value:** `75`
   * **To change the value to 50:** Modify the declaration to `int brightnessSetting = 50;` or assign it later using `brightnessSetting = 50;`.

2. **Why is `bool` suitable for `switchOn`, while `int` is suitable for `brightnessSetting`?**
   * `bool` represents binary two-state logic (`true` / `false` or `ON` / `OFF`), making it appropriate for a switch.
   * `int` stores whole numerical values within a range (e.g., `0` to `100`), which is necessary to represent varying levels of brightness.

3. **Predict the output when `brightnessSetting` is 80 and `switchOn` is `false`.**
   * The output lamp brightness will be **`0`**. Since the switch is off (`false`), the lamp outputs zero brightness regardless of the setting.

4. **Are `switchOn` and `switchon` the same variable? Explain.**
   * **No.** C++ and Arduino are strictly case-sensitive languages. The lowercase `o` in `switchon` makes it an entirely different identifier from `switchOn`.

5. **What values are passed to `getLampBrightness()`, and what does it return?**
   * **Values passed (arguments):** A boolean value for `switchOn` (representing power state) and an integer value for `brightnessSetting` (representing intended intensity).
   * **Return value:** It returns an integer (`int`) representing the effective lamp brightness (`brightnessSetting` if the switch is `true`, or `0` if the switch is `false`).

6. **If `lampBrightness` is declared inside `setup()`, can `loop()` access it directly? Explain.**
   * **No.** Variables declared inside `setup()` possess local scope and are confined solely to that function block. Once `setup()` finishes executing, those local variables are destroyed and are inaccessible to `loop()`. To make it accessible to both, it must be declared as a global variable outside of all functions.
