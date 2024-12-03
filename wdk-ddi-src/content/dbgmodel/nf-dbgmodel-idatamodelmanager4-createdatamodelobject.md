---
UID: NF:dbgmodel.IDataModelManager4.CreateDataModelObject
tech.root: debugger
title: IDataModelManager4::CreateDataModelObject
ms.date: 12/03/2024
targetos: Windows
description: The CreateDataModelObject method is a simple helper wrapper for creating objects that are data models.
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
 - IDataModelManager4::CreateDataModelObject
f1_keywords:
 - IDataModelManager4::CreateDataModelObject
 - dbgmodel/IDataModelManager4::CreateDataModelObject
dev_langs:
 - c++
helpviewer_keywords:
 - CreateDataModelObject
---

## -description

The CreateDataModelObject method is a simple helper wrapper to create objects which are data models -- that is objects which are going to be attached as parent models to other objects. All such objects must support the data model concept via [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md). This method creates a new blank synthetic object with no explicit context and adds the inpassed [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md) as the newly created object's implementation of the data model concept. This can similarly be accomplished with calls to CreateSyntheticObject and SetConcept.

## -parameters

### -param dataModel

The implementation of [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md) which will be automatically added to the newly created object as its implementation of the data model concept.

### -param object

The newly created synthetic object (with the data model concept set) will be returned here.

## -returns

This method returns HRESULT.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

// We need some IDataModelConcept implementation.  Provide a 
// minimal one for example purposes.
class MyDataModel :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<
            Microsoft::WRL::RuntimeClassType::ClassicCom
            >,
        IDataModelConcept
        >
{
public:

    IFACEMETHOD(InitializeObject)(
        _In_ IModelObject * /*pContextObject*/, 
        _In_opt_ IDebugHostTypeSignature * /*pMatchingSignature*/, 
        _In_opt_ IDebugHostSymbolEnumerator * /*pWildcardMatches*/
        )
    {
        return S_OK;
    }

    IFACEMETHOD(GetName)(_Out_ BSTR *pModelName)
    {
        *pModelName = nullptr;
        return E_NOTIMPL;
    }
};

ComPtr<MyDataModel> spMyModel = Microsoft::WRL::Make<MyDataModel>();
if (spMyModel != nullptr)
{
    ComPtr<IModelObject> spDataModelObject;
    if (SUCCEEDED(spManager->CreateDataModelObject(spMyModel.Get(),
                                                   &spDataModelObject)))
    {
        // spDataModelObject is now a data model object and can be attached
        // as a parent to any other object via AddParentModel().
    }
}
```

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)