
# BloxFun

A release of 2011-2015 [![Play on Roblox](https://shields.io)](https://roblox.com)
 Trying to Mimic PC Features;
```
+ Studio Mobile (SL Without API Key)
+ Now With Actual Chat (since Roblox Desperately begged AI Age Verification) 
```
## Installation

Install Bloxfun Via the Releases

```bash
  echo "this isn't bash
  cd not-bash-yet-this-is-just-dummy-bash-code
```
    
## Optimizations

What optimizations did you make in your code? E.g. refactors, performance improvements, accessibility


## Contributing

Contributions are always welcome!

See `contributing.md` for ways to get started.

Please adhere to this project's `code of conduct`.


## License

[Apache](https://choosealicense.com/licenses/apache/)


## Used By

This project is used by the following companies:

- luauy's `ludev`
- luauy's satisfactory thinking thinks


## Usage/Examples

# 🏕️ The .campcode Language Specification

`campcode` is a lightweight, ultra-simple custom scripting language designed for sandbox environments and engine logic. It uses a strict wrapper-based syntax that is easy for parsers to read and highly efficient to execute via the command line.

---

## 📜 Code Example (`main.campcode`)

Save the following dummy code as a `.campcode` file to test logical gates, boolean variables, type checks, and classic UI event bindings:

```text
! setl func start() !
lfunc start()
    outprint "Initializing camp UI systems..."
    
    # 🎨 UI Element Fetching & Binding
    laddg parent_element engine.script.Parent
    laddg menu_frame parent_element.WaitForChild("MenuFrame")
    
    # ☯️ Classic Lua Boolean Setup
    set menu_is_open false
    set system_override true
    
    # 🖱️ Event Binding
    bind_event parent_element.MouseButton1Click toggle_menu
    log_success "UI Events successfully bound with native boolean trackers."

! setl func toggle_menu() !
lfunc toggle_menu()
    # 🛡️ Classic Lua Logic Evaluation (Not Gate)
    not menu_is_open menu_is_open
    
    # Check data integrity using type assertions
    type var_type menu_is_open
    
    ! check var_type == "boolean" !
    if_true
        set_prop menu_frame.Visible menu_is_open
        cprint "Menu visibility state flipped dynamically."
    if_false
        log_warn "Type mismatch! Variable is not a true boolean."
```

---

## ☯️ Classic Lua Booleans & Logical Gates

`campcode` preserves the classic truth evaluations of early game engines, treating only `false` and `nil` as falsy values, while `0` and empty strings `""` remain evaluationally `true`.

### 🔄 Logical Gate Operators
To evaluate values without syntax bloat, logical operations run inline and overwrite or assign values dynamically:
* **`not [target] [source]`**: Inverts the truthiness of the `[source]` variable and saves it into `[target]`.
  * *Example:* `not state state` *(Flips a true/false toggle)*
* **`and [target] [val1] [val2]`**: Evaluates if both inputs are truthy. Assigns the resulting evaluated value to `[target]`.
* **`or [target] [val1] [val2]`**: Evaluates if either input is truthy. Assigns the first truthy value to `[target]`.

### 🔍 Metadata & Type Extraction
* **`type [target] [var]`**: Extracts the primitive engine data type of `[var]` as a string descriptor and maps it to `[target]`.
  * *Expected Outputs:* `"boolean"`, `"string"`, `"number"`, `"nil"`, `"userdata"`
* **`nilify [var]`**: Completely clears a memory register, dropping its value back to a raw global `nil` state.

---

## 🎨 UI Component Bindings & Event Listening

`campcode` implements a high-level UI binding API that mirrors object-oriented game engines (like Roblox's classic `Instance` and `Event` pipelines).

* **`laddg [var] [path/property]`** / Alias: `local_add_gui`, `lgetg`: Looks up a physical engine UI asset or a UI hierarchy tree path and binds it to a local runtime variable `[var]`.
* **`bind_event [ui_element.Event] [function_name]`** / Alias: `connect`: Listens for a specific physical UI interaction and automatically runs a target `lfunc` block when the event fires.
* **`set_prop [ui_element.Property] [value]`** / Alias: `setp`: Dynamically changes a UI property (like text, color, position, or toggling visibility state directly via a boolean).

---

## 🔒 Security, Obfuscation & Anti-Tamper

To protect server-side or proprietary game scripts from malicious manipulation, `campcode` supports native low-level protection hooks designed for automated obfuscators.

* **`sbin [var] [hex_or_binary_string]`** / Alias: `setbinary`: Directly loads compiled, raw binary or hexadecimal machine strings into an executable object variable `[var]`. 
* **`frch [var]`** / Alias: `antitamper`, `filecheck`: Triggers an instant cryptographic checksum of the running file structure. Returns `1` into `[var]` if tampered with, otherwise `0`.

---

## 🖨️ Output Commands & Aliases

The language features built-in routing for string outputs, separating standard terminal debugging, app notifications, and system logs.


| Command | Aliases | Target Destination / Behavior |
| :--- | :--- | :--- |
| `cprint` | `chatprint` | App / Game Visual Chat UI |
| `outprint` | `oprint`, `outp`, `pout` | System Terminal / Console Window Only |
| `log_info` | `loginfo`, `linf` | Standard tracking log file (Appends timestamp) |
| `log_warn` | `logwarn`, `lwrn` | System log stream formatted in yellow text |
| `log_success`| `logok`, `lsuc` | System log stream formatted in green text |

---

## 🧮 Math Operations & Randomness

To avoid complex nested equations, math in `campcode` runs linearly on target variables.

* **`rand [var] [min] [max]`** / Alias: `random`, `rnd`: Generates a random integer between `[min]` and `[max]`.
* **`set [var] [value]`**: Assigns a fresh starting number, string, or boolean value to a variable.
* **`add [var] [value]`**, **`sub`**, **`mul`**, **`div`**: Standard mathematical operations execution.

---

## 🧠 Logical Wrappers & Control Flow

To keep parsing simple, conditional checks are wrapped in exclamation marks `!`, mirroring the function declaration style.

* **Conditionals:** `! check [var] [operator] [value] !` followed by immediate `if_true` or `if_false` execution blocks.
* **Operators Supported:** `==`, `!=`, `<`, `>`, `<=`, `>=`
* **String Concatenation:** Merges static text and current variable values using the `+` operator.

---

## 💻 CLI Features & Inspection

You can inspect, debug, and profile the structure of your `.campcode` files directly from your system command line without running the full runtime engine.

### 1. File Obfuscation & Pre-compilation
```bash
campcode --obfuscate main.campcode --out secure.campcode
```

### 2. Syntax Validation Check
```bash
campcode --validate main.campcode
```
**Output:**
```text
[Validation]: SUCCESS
  -> 2/2 Functions properly closed.
  -> 1/1 Conditional wrappers properly bounded.
  -> li(on /is 82! ? (/**"  {×\=∆’~`
```
