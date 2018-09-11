---
title: nonextensible | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f24aa8b1aa6b4e2e996ec22062263f785d730d0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222584"
---
# <a name="nonextensible"></a>nonextensible

Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не может быть расширен с помощью дополнительных членов во время выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
[nonextensible]
```

## <a name="remarks"></a>Примечания

**Nonextensible** атрибут C++ имеет ту же функциональность, что [nonextensible](/windows/desktop/Midl/nonextensible) описании атрибута MIDL.

Использование **nonextensible** также требуется [oleautomation](../windows/oleautomation.md) атрибута.

## <a name="example"></a>Пример

В следующем коде показано один из способов использования **nonextensible** атрибут:

```cpp
// cpp_attr_ref_nonextensible.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export] typedef long HRESULT;

[dual, nonextensible, ms_union, oleautomation,
uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   HRESULT procedure (int i);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**interface**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|`dual` и `oleautomation`, или `dispinterface`|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  