# CSharp

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [Methods Index](Methods-Index) | [Properties Index](Properties-Index)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Methods


### Compile

Compiles C# code

```python
def Compile(code):
"""
Compiles C# code

Args:
code (str): Code to compile

Returns:
Compiled code object

"""
```


### CompileAndRun

Compiles and runs C# code

**Overload 1:**

```python
def CompileAndRun(code):
"""
Compiles and runs C# code

Args:
code (str): Code to compile and run

Returns:
Updated dictionary of variables

"""
```

**Overload 2:**

```python
def CompileAndRun(code, variables):
"""
Compiles and runs C# code

Args:
code (str): Code to compile and run
variables (IronPython.Runtime.PythonDictionary): Dictionary of variables

Returns:
Updated dictionary of variables

"""
```


### Run

Runs compiled C# code

**Overload 1:**

```python
def Run(script):
"""
Runs compiled C# code

Args:
script (Microsoft.CodeAnalysis.Scripting.Script{System.Object[]}): Compiled code object to run

Returns:
Updated dictionary of variables

"""
```

**Overload 2:**

```python
def Run(script, variables):
"""
Runs compiled C# code

Args:
script (Microsoft.CodeAnalysis.Scripting.Script{System.Object[]}): Compiled code object to run
variables (IronPython.Runtime.PythonDictionary): Dictionary of variables or None for no variables

Returns:
Updated dictionary of variables

"""
```

---
**[⬆ Back to Top](#csharp)**
