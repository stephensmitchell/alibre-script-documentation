# AssembledSubAssembly

[ Back to Classes](Classes) | [Documentation Home](../README.md) | [All Classes](Classes)

- Namespace: `AlibreScript.API`
- Kind: `Class`

## Properties

### Configurations
Type: `Object`
A list of configurations defined on the assembly

### Name
Type: `Object`
Name of the subassembly

## Methods


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


### GetMappedOccurrence

Gets the occurrence of the sub-assembly mapped into the
occurrence structure of a specific assembly
This occurrence can be used to create constraints in the specific
sub-assembly using the part

```python
def GetMappedOccurrence(assembly):
"""
Gets the occurrence of the sub-assembly mapped into the occurrence structure of a specific assembly This occurrence can be used to create constraints in the specific sub-assembly using the part

Args:
assembly (AlibreX.IADAssemblySession): Assembly for occurrence structure

Returns:
Mapped occurrence or null if not found

"""
```

---
**[⬆ Back to Top](#assembledsubassembly)**
