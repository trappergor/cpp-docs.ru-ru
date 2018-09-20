---
title: call_as | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 072c5b34d539e695f534dbafdf4afcd69a2272ab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415685"
---
# <a name="callas"></a>call_as

Позволяет [локального](../windows/local-cpp.md) функции для сопоставления с удаленной функции так, что при вызове удаленной функции локальной функции.

## <a name="syntax"></a>Синтаксис

```cpp
[ call_as(
   function
) ]
```

### <a name="parameters"></a>Параметры

*function*<br/>
Локальная функция, которую требуется вызывать при вызове удаленной функции.

## <a name="remarks"></a>Примечания

**Call_as** атрибут C++ имеет ту же функциональность, что [call_as](/windows/desktop/Midl/call-as) описании атрибута MIDL.

## <a name="example"></a>Пример

В следующем коде показано, как можно использовать **call_as** для сопоставления функции не поддерживающие удаленное взаимодействие (`f1`) функции удаленного взаимодействия (`Remf1`):

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[локальный](../windows/local-cpp.md)  