---
title: Уникальный (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: 9d049983bb072e073180f1821f04b79e5f5c7444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512849"
---
# <a name="unique-c"></a>unique (C++)

Указывает уникальный указатель.

## <a name="syntax"></a>Синтаксис

```cpp
[unique]
```

## <a name="remarks"></a>Примечания

**Уникальный** атрибут C++ имеет ту же функциональность, что [уникальный](/windows/desktop/Midl/unique) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [ref](ref-cpp.md) пример для использовать **уникальный**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**TypeDef**, **структуры**, **объединение**, параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)