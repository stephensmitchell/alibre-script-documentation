# Configuration

**[Home](Home) | [Classes](Classes) | [Methods](Methods-Index) | [Properties](Properties-Index) | [Members](Members-Index)**

** Location:**[Configuration & Parameters](Classes#configuration) Configuration

**Namespace:** `AlibreScript.API` | **Kind:** Class

The Configuration class provides functionality for managing part and assembly configurations, including activation state and configuration locks.

## Related Classes
- [Part](Part) - Contains configurations
- [Assembly](Assembly) - Assembly configurations
- [GlobalParameters](GlobalParameters) - Configuration parameters
- [LockTypes](LockTypes) - Lock type definitions
- [Parameter](Parameter) - Configuration parameters

## Quick Navigation
- [Properties](#properties) - Configuration state and identity
- [Methods](#methods) - Configuration operations

## Properties

### IsActive
Type: `Object`
True if the configuration is currently active

### Name
Type: `Object`
The name of the configuration

## Methods


### SetLocks

Sets the locks on the configuration

```python
def SetLocks(locks):
"""
Sets the locks on the configuration

Args:
locks (LockTypes): Locks to set

"""
```

---
**[⬆ Back to Top](#configuration)**
