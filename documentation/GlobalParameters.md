# GlobalParameters

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Configuration & Parameters](Classes#configuration) GlobalParameters

**Namespace:** `AlibreScript.API` | **Kind:** Class

The GlobalParameters class provides comprehensive functionality for managing global parameters, configurations, and parameter relationships across parts and assemblies.

## Related Classes
- [Parameter](Parameter) - Individual parameter management
- [Configuration](Configuration) - Configuration operations
- [ParameterTypes](ParameterTypes) - Parameter type definitions
- [ParameterUnits](ParameterUnits) - Parameter unit definitions
- [Part](Part), [Assembly](Assembly) - Use global parameters

## Quick Navigation
- [Properties](#properties) - Parameter collections and identity
- [Methods](#methods) - Parameter operations
- [Configuration Methods](#configuration-methods) - Configuration management
- [File Operations](#file-operations) - Save and load operations

## Properties

### Configurations
Type: `Object`
A list of configurations

### Name
Type: `Object`
Name of the global parameters

### Parameters
Type: `Object`
A list of parameters

## Methods


### GlobalParameters

Opens an existing global parameters set

**Overload 1:**

```python
def GlobalParameters(folder, name):
"""
Opens an existing global parameters set

Args:
folder (str): Folder containing global parameters
name (str): Name of global parameters to open

"""
```

**Overload 2:**

```python
def GlobalParameters(name):
"""
Creates a new global parameters set

Args:
name (str): Name of new global parameters set

"""
```

**Overload 3:**

```python
def GlobalParameters(name, create_new):
"""
Creates a new global parameters set or accesses an already opened global parameters set

Args:
name (str): Name of global parameters set to create or access
create_new (bool): True to create a new global parameters set, false to access an opened global parameters

"""
```


### AddConfiguration

Adds a configuration to the global parameters set

**Overload 1:**

```python
def AddConfiguration(name):
"""
Adds a configuration to the global parameters set

Args:
name (str): Name of configuration

Returns:
New configuration

"""
```

**Overload 2:**

```python
def AddConfiguration(name, base_configuration_name):
"""
Adds a configuration to the global parameters set using another configuration as a base

Args:
name (str): Name of configuration
base_configuration_name (str): Name of base configuration to use

Returns:
New configuration

"""
```


### AddParameter

Adds a parameter to the global parameters set

**Overload 1:**

```python
def AddParameter(name, type, value):
"""
Adds a parameter to the global parameters set

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
value (float): Value for parameter

Returns:
New parameter

"""
```

**Overload 2:**

```python
def AddParameter(name, type, equation):
"""
Adds a parameter to the global parameters set

Args:
name (str): Name of parameter
type (ParameterTypes): Type of parameter
equation (str): Equation for parameter

Returns:
New parameter

"""
```


### GetConfiguration

Gets a configuration with a specific name

```python
def GetConfiguration(name):
"""
Gets a configuration with a specific name

Args:
name (str): Name of confguration

Returns:
Configuration object

"""
```


### GetParameter

Gets a parameter with a specific name

```python
def GetParameter(name):
"""
Gets a parameter with a specific name

Args:
name (str): Name of parameter

Returns:
Parameter object

"""
```


### Save

Saves the global parameters set to a specific folder

```python
def Save(folder):
"""
Saves the global parameters set to a specific folder

Args:
folder (str): Folder to save to

"""
```


### SaveAs

Saves the global parameters set to a specific folder with a new name

```python
def SaveAs(folder, new_name):
"""
Saves the global parameters set to a specific folder with a new name

Args:
folder (str): Folder to save to
new_name (str): New name for global parameters set

"""
```

---
**[⬆ Back to Top](#globalparameters)**
