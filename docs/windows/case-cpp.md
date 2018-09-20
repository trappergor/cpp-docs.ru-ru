---
title: регистр (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6b610ce888e91ed8029c4166fa79a847d700dba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436524"
---
# <a name="case-c"></a>case (C++)

Используется с [switch_type](../windows/switch-type.md) атрибут в **объединение**.

## <a name="syntax"></a>Синтаксис

```cpp
[ case(
   value
) ]
```

#### <a name="parameters"></a>Параметры

*значение*<br/>
Возможное значение ввода, для которого вы хотите предоставить обработки. Тип **значение** может принимать одно из следующих типов:

- `int`

- `char`

- `boolean`

- `enum`

или идентификатор такого типа.

## <a name="remarks"></a>Примечания

**Случай** атрибут C++ имеет ту же функциональность, что **случай** описании атрибута MIDL. Этот атрибут используется только с [switch_type](../windows/switch-type.md) атрибута.

## <a name="example"></a>Пример

В следующем коде показано использование **случай** атрибут:

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Член **класс** или **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)  