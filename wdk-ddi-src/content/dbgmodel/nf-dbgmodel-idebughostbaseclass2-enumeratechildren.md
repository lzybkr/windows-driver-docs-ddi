---
UID: NF:dbgmodel.IDebugHostBaseClass2.EnumerateChildren
tech.root: debugger
title: IDebugHostBaseClass2::EnumerateChildren
ms.date: 12/16/2024
targetos: Windows
description: The EnumerateChildren method gets an enumerator capable of enumerating all children of a given symbol.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass2::EnumerateChildren
f1_keywords:
 - IDebugHostBaseClass2::EnumerateChildren
 - dbgmodel/IDebugHostBaseClass2::EnumerateChildren
dev_langs:
 - c++
helpviewer_keywords:
 - EnumerateChildren
---

## -description

The EnumerateChildren method returns an enumerator which will enumerate all children of a given symbol. For a C++ type, for example, the base classes, fields, member functions, and the like are all considered children of the type symbol.

## -parameters

### -param kind

Indicates what kinds of child symbols the caller wishes to enumerate. If the flat value Symbol is passed, all kinds of child symbols will be enumerated.

### -param name

If specified, only child symbols with a name as given in this argument will be enumerated.

### -param ppEnum

An enumerator which enumerates child symbols of the specified kind and name will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostType> spType; /* get the type of an object */

// Enumerate every field of this type.  Note that this *WILL NOT* enumerate 
// fields of base classes!
ComPtr<IDebugHostSymbolEnumerator> spEnum;
if (SUCCEEDED(spType->EnumerateChildren(SymbolField, nullptr, &spEnum)))
{
    ComPtr<IDebugHostSymbol> spFieldSymbol;
    HRESULT hr = S_OK;
    while (SUCCEEDED(hr))
    {
        hr = spEnum->GetNext(&spFieldSymbol);
        if (SUCCEEDED(hr))
        {
            ComPtr<IDebugHostField> spField;
            if (SUCCEEDED(spFieldSymbol.As(&spField))) /* should always succeed */
            {
                // spField is each field of the type in turn
            }
        }
    }

    // hr == E_BOUNDS : we hit the end of the enumerator
    // hr == E_ABORT  : user requested interruption, propagate upwards immediately
}
```

## -see-also

[IDebugHostBaseClass2 interface](nn-dbgmodel-idebughostbaseclass2.md)