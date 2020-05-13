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
ms.openlocfilehash: e11d31904fd8e54049f69ee4f6530d511c8c7f4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187756"
---
# <a name="_variant_t-class"></a>Класс _variant_t

**Блок, относящийся только к системам Microsoft**

Объект **_variant_t** инкапсулирует тип данных `VARIANT`. Класс управляет выделением и освобождением ресурсов и делает вызовы функций `VariantInit` и `VariantClear` соответствующим образом.

### <a name="construction"></a>Строительство

|||
|-|-|
|[_variant_t](../cpp/variant-t-variant-t.md)|Конструирует объект **_variant_t** .|

### <a name="operations"></a>Операции

|||
|-|-|
|[Присоединить](../cpp/variant-t-attach.md)|Присоединяет объект `VARIANT` к объекту **_variant_t** .|
|[Clear](../cpp/variant-t-clear.md)|Очищает инкапсулированный `VARIANT` объект.|
|[ChangeType](../cpp/variant-t-changetype.md)|Изменяет тип объекта **_variant_t** на указанный `VARTYPE`.|
|[Отсоединить](../cpp/variant-t-detach.md)|Отсоединяет инкапсулированный `VARIANT` объект от этого **_variant_t** объекта.|
|[SetString](../cpp/variant-t-setstring.md)|Присваивает строку этому объекту **_variant_t** .|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](../cpp/variant-t-operator-equal.md)|Присваивает новое значение существующему объекту **_variant_t** .|
|[оператор = =,! =](../cpp/variant-t-relational-operators.md)|Сравните два **_variant_t** объектов на равенство или неравенство.|
|[Средства извлечения](../cpp/variant-t-extractors.md)|Извлечение данных из инкапсулированного `VARIANT` объекта.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<комутил. h >

**Lib:** комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t является собственным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>См. также раздел

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)
