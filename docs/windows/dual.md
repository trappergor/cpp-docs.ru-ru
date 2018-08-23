---
title: двойной | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dual
dev_langs:
- C++
helpviewer_keywords:
- dual attribute
ms.assetid: 5d4a9069-d819-42cd-ba56-bbcda17157d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3727fc70698d3202734db7bbe72773cbe49bffb9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592917"
---
# <a name="dual"></a>dual

Помещает интерфейс в IDL-файл как сдвоенный интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
[dual]
```

## <a name="remarks"></a>Примечания

Когда **двойной** интерфейсу предшествует атрибут C++, это вызывает интерфейс необходимо поместить в блок library созданного IDL-файла.

## <a name="example"></a>Пример

В следующем коде приведен, использующий блок атрибутов **двойной** до определения интерфейса:

```cpp
// cpp_attr_ref_dual.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), dual]

__interface IStatic : IDispatch
{
   HRESULT Func1(int i);
   [   propget,
      id(1),
      bindable,
      displaybind,
      defaultbind,
      requestedit
   ]
   HRESULT P1([out, retval] long *nSize);
   [   propput,
      id(1),
      bindable,
      displaybind,
      defaultbind,
      requestedit
   ]
   HRESULT P1([in] long nSize); 
};

[cpp_quote("#include file.h")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|`dispinterface`|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Список атрибутов по использованию](../windows/attributes-by-usage.md)  
[Custom](../windows/custom-cpp.md)  
[dispinterface](../windows/dispinterface.md)  
[object](../windows/object-cpp.md)  
[__interface](../cpp/interface.md)  