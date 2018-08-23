---
title: Привязываемые | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.bindable
dev_langs:
- C++
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4c529abb1ade786bf7ec0a2d5cff5c49f6197be7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601593"
---
# <a name="bindable"></a>bindable

Указывает, что свойство поддерживает привязку данных.

## <a name="syntax"></a>Синтаксис

```cpp
[bindable]
```

## <a name="remarks"></a>Примечания

**Bindable** атрибут C++ имеет ту же функциональность, что [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738) описании атрибута MIDL. Его можно использовать на свойства, определенные с [propget](../windows/propget.md), [propput](../windows/propput.md), или [propputref](../windows/propputref.md) атрибуты, или можно вручную определить метод привязки.

В следующих примерах MFC показано использование **bindable**:

- [Примеры элементов управления: Элементы управления ActiveX на основе MFC](http://msdn.microsoft.com/a44adf86-0ba0-4504-bedb-512b6cba2e63)

- [Кр образец: Элемент управления ActiveX](http://msdn.microsoft.com/9ba34d04-280e-49f4-90ae-41a6be44c95b)

- [Образец TESTHELP: Элемент управления ActiveX с помощью подсказки и помощь](http://msdn.microsoft.com/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)

## <a name="example"></a>Пример

В следующем коде показано, как можно использовать **bindable** свойства:

```cpp
// cpp_attr_ref_bindable.cpp
// compile with: /LD
#include <windows.h>
[
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),
   dispinterface,
   helpstring("property demo Interface")  
]
__interface IPropDemo : IDispatch {

   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();
};

[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[defaultbind](../windows/defaultbind.md)  
[displaybind](../windows/displaybind.md)  
[immediatebind](../windows/immediatebind.md)  
[requestedit](../windows/requestedit.md)  