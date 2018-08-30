---
title: ограниченные | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8d226f508f5f5e8c717bd671413f21377c0ae01
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202294"
---
# <a name="restricted"></a>restricted

Указывает, что член модуля, интерфейс или диспетчерский интерфейс не может вызываться произвольным образом.

## <a name="syntax"></a>Синтаксис

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Параметры

*interfaces*  
Один или несколько интерфейсов, которые не может вызываться произвольным образом для COM-объекта. Этот параметр допустим только в том случае, при применении к классу.

## <a name="remarks"></a>Примечания

**Ограниченных** атрибут C++ имеет ту же функциональность, что [ограниченных](/windows/desktop/Midl/restricted) описании атрибута MIDL.

## <a name="example"></a>Пример

Ниже показано, как использовать **ограниченных** атрибут:

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод, интерфейса **интерфейс**, **класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**Компонентный класс** (при применении к **класс** или **структуры**)|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  