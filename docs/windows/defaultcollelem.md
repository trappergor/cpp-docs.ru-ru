---
title: defaultcollelem | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultcollelem
dev_langs:
- C++
helpviewer_keywords:
- defaultcollelem attribute
ms.assetid: 3dbbd293-8b83-4f70-a36b-64cc1d0b6713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b65cb8c9fb5f46568d5449b3e54157f63a16b3e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422536"
---
# <a name="defaultcollelem"></a>defaultcollelem

Используется для оптимизации кода Visual Basic.

## <a name="syntax"></a>Синтаксис

```cpp
[defaultcollelem]
```

## <a name="remarks"></a>Примечания

**Defaultcollelem** атрибут C++ имеет ту же функциональность, что [defaultcollelem](/windows/desktop/Midl/defaultcollelem) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показан метод интерфейса с помощью **defaultcollelem** атрибут:

```cpp
// cpp_attr_ref_defaultcollelem.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyForm
{
   [propget, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, defaultcollelem, displaybind,
   defaultbind, requestedit] HRESULT P1([in] long nSize);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)  