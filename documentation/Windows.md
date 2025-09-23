# Windows

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Utilities & System](Classes#utilities) Windows

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Windows class provides functionality for managing Windows forms, dialogs, and user interface operations within the Alibre Design environment.

## Related Classes
- [WindowsInputTypes](WindowsInputTypes) - Input type definitions
- [CSharp](CSharp) - C# integration utilities
- [Part](Part), [Assembly](Assembly) - Use Windows operations
- [GlobalParameters](GlobalParameters) - Windows for parameters

## Quick Navigation
- [Methods](#methods) - All available operations
- [Dialog Methods](#dialog-methods) - File dialogs and user input
- [Form Methods](#form-methods) - Form management
- [Display Methods](#display-methods) - Window display operations

## Methods


### CloseForm

Close all currently open forms for a specific session

```python
def CloseForm(session_identifier):
"""
Close all currently open forms for a specific session

Args:
session_identifier (str): Identifier for session

"""
```


### DisableInput

Disables an input

```python
def DisableInput(index):
"""
Disables an input

Args:
index (int): Index of the input

"""
```


### EnableInput

Enables an input

```python
def EnableInput(index):
"""
Enables an input

Args:
index (int): Index of the input

"""
```


### ErrorDialog

Shows an error window

```python
def ErrorDialog(message, title):
"""
Shows an error window

Args:
message (str): Error message
title (str): Title of window

"""
```


### GetDisplayedForm

Gets the currently displayed form for a specific session

```python
def GetDisplayedForm(session_identifier):
"""
Gets the currently displayed form for a specific session

Args:
session_identifier (str): Identifier of session

Returns:
Displayed form or null for none

"""
```


### GetInputValue

Gets the current value of an input

```python
def GetInputValue(index):
"""
Gets the current value of an input

Args:
index (int): Index of the input

Returns:
Current value

"""
```


### InfoDialog

Shows an information window

```python
def InfoDialog(message, title):
"""
Shows an information window

Args:
message (str): Message to show
title (str): Title of window

"""
```


### OpenFileDialog

Prompts user to select a file

```python
def OpenFileDialog(title, filter, default_extension):
"""
Prompts user to select a file

Args:
title (str): Title of dialog window
filter (str): File filter, example filter: 'Part Files|*.AD_PRT'
default_extension (str): Default file extension, e.g. '.AD_PRT'

Returns:
Path and name of selected file or empty string if canceled

"""
```


### OptionsDialog

Shows a dialog prompting the user to enter values

**Overload 1:**

```python
def OptionsDialog(title, inputs, input_area_width):
"""
Shows a dialog prompting the user to enter values

Args:
title (str): Title of dialog window
inputs (list): List of input definitions [[Name, Type, DefaultValue], [...]]
input_area_width (int): Width of input area, optional

Returns:
List of entered values

"""
```

**Overload 2:**

```python
def OptionsDialog(title, inputs, input_area_width, input_changed_callback, update_user_interface_callback):
"""
Shows a dialog prompting the user to enter values

Args:
title (str): Title of dialog window
inputs (list): List of input definitions\n [[Name, Type, DefaultValue, OptionalSettings], [...]]\n Example: ['Image', WindowsInputTypes.Image, 'Logo.png']
input_area_width (int): Width of input area
input_changed_callback (object): Function called when an input is changed
update_user_interface_callback (object): Function called after dialog is created to update the state of the dialog

Returns:
List of entered values

"""
```


### QuestionDialog

Shows a question window

```python
def QuestionDialog(question, title):
"""
Shows a question window

Args:
question (str): Question to show
title (str): Title of window

Returns:
true if 'yes' was clicked, false if 'no' was clicked

"""
```


### SaveFileDialog

Prompts user to save a file

```python
def SaveFileDialog(title, filter, default_extension):
"""
Prompts user to save a file

Args:
title (str): Title of dialog window
filter (str): File filter, example filter: 'Part Files|*.AD_PRT'
default_extension (str): Default file extension, e.g. '.AD_PRT'

Returns:
Path and name of selected file or empty string if canceled

"""
```


### SelectFolderDialog

Prompts the user to select a folder

```python
def SelectFolderDialog(current_folder, description):
"""
Prompts the user to select a folder

Args:
current_folder (str): The current folder, if any
description (str): Description of what is being chosen, shown to user

Returns:
Path of selected folder or empty if canceled

"""
```


### SetInputValue

Sets the current value for an input

```python
def SetInputValue(index, value):
"""
Sets the current value for an input

Args:
index (int): Index of the input
value (object): Value to show

"""
```


### SetStringList

Updates the list of strings for a stringlist input

```python
def SetStringList(index, strings):
"""
Updates the list of strings for a stringlist input

Args:
index (int): Index of the stringlist input
strings (object): New list of strings to show

"""
```


### UtilityDialog

Shows a dialog prompting the user to enter values
The dialog remains open until the user clicks on the close button
A callback function is called to give the input values to the script

**Overload 1:**

```python
def UtilityDialog(title, action_button_text, action_button_callback, input_changed_callback, inputs, input_area_width):
"""
Shows a dialog prompting the user to enter values The dialog remains open until the user clicks on the close button A callback function is called to give the input values to the script

Args:
title (str): Title of dialog window
action_button_text (str): Text for action button
action_button_callback (object): Function called when the action button is clicked
input_changed_callback (object): Function called when an input is changed
inputs (list): List of input definitions [[Name, Type, DefaultValue, OptionalSettings], [...]]
input_area_width (int): Width of dialog input area, optional

"""
```

**Overload 2:**

```python
def UtilityDialog(title, action_button_text, action_button_callback, input_changed_callback, inputs, input_area_width, update_user_interface_callback):
"""
Shows a dialog prompting the user to enter values The dialog remains open until the user clicks on the close button A callback function is called to give the input values to the script

Args:
title (str): Title of dialog window
action_button_text (str): Text for action button
action_button_callback (object): Function called when the action button is clicked
input_changed_callback (object): Function called when an input is changed
inputs (list): List of input definitions\n [[Name, Type, DefaultValue, OptionalSettings], [...]]\n Example: ['Image', WindowsInputTypes.Image, 'Logo.png']
input_area_width (int): Width of dialog input area
update_user_interface_callback (object): Function called after dialog is created to update the state of the dialog

"""
```

---
**[⬆ Back to Top](#windows)**
