---
title: Класс _variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: 3873452afca0159cba815a2cb290ebb6e62aff07
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842563"
---
# <a name="_variant_t-class"></a>Класс _variant_t

**Блок, относящийся только к системам Microsoft**

Объект **_variant_t** инкапсулирует `VARIANT` тип данных. Класс управляет выделением и освобождением ресурсов и делает вызовы функций `VariantInit` и `VariantClear` соответствующим образом.

### <a name="construction"></a>Строительство

| Имя | Описание |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | Конструирует объект **_variant_t** . |

### <a name="operations"></a>Operations

| Имя | Описание |
|--|--|
| [Attach](../cpp/variant-t-attach.md) | Присоединяет `VARIANT` объект к объекту **_variant_t** . |
| [Clear](../cpp/variant-t-clear.md) | Очищает инкапсулированный `VARIANT` объект. |
| [ChangeType](../cpp/variant-t-changetype.md) | Изменяет тип объекта **_variant_t** на указанный `VARTYPE` . |
| [Отсоединить](../cpp/variant-t-detach.md) | Отсоединяет инкапсулированный `VARIANT` объект от этого **_variant_t** объекта. |
| [SetString](../cpp/variant-t-setstring.md) | Присваивает строку этому объекту **_variant_t** . |

### <a name="operators"></a>Операторы

| Имя | Описание |
|--|--|
| [Оператор =](../cpp/variant-t-operator-equal.md) | Присваивает новое значение существующему объекту **_variant_t** . |
| [оператор = =,! =](../cpp/variant-t-relational-operators.md) | Сравните два **_variant_t** объектов на равенство или неравенство. |
| [Средства извлечения](../cpp/variant-t-extractors.md) | Извлечение данных из инкапсулированного `VARIANT` объекта. |

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:**\<comutil.h>

**Lib:** комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t является собственным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>См. также раздел

[Классы поддержки COM компилятора](../cpp/compiler-com-support-classes.md)
