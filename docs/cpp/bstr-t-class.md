---
title: Класс _bstr_t
ms.date: 11/04/2016
f1_keywords:
- _bstr_t
helpviewer_keywords:
- BSTR object
- _bstr_t class
- BSTR object [C++], COM encapsulation
ms.assetid: 58841fef-fe21-4a84-aab9-780262b5201f
ms.openlocfilehash: 3ef89c6f6742d528c427c49fd2a62d8820625e79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190382"
---
# <a name="_bstr_t-class"></a>Класс _bstr_t

**Блок, относящийся только к системам Microsoft**

Объект `_bstr_t` инкапсулирует [тип данных BSTR](/previous-versions/windows/desktop/automat/bstr). Класс управляет выделением и освобождением ресурсов с помощью вызовов функций для `SysAllocString` и `SysFreeString` и других `BSTR` API, когда это уместно. Класс **_bstr_t** использует подсчет ссылок во избежание чрезмерных издержек.

### <a name="construction"></a>Строительство

|||
|-|-|
|[_bstr_t](../cpp/bstr-t-bstr-t.md)|Формирует объект `_bstr_t`.|

### <a name="operations"></a>Операции

|||
|-|-|
|[Assign](../cpp/bstr-t-assign.md)|Копирует строку `BSTR` в строку `BSTR`, инкапсулированную объектом `_bstr_t`.|
|[Присоединить](../cpp/bstr-t-attach.md)|Связывает упаковщик `_bstr_t` со строкой `BSTR`.|
|[copy](../cpp/bstr-t-copy.md)|Создает копию инкапсулированного объекта `BSTR`.|
|[Отсоединить](../cpp/bstr-t-detach.md)|Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).|
|[GetAddress](../cpp/bstr-t-getaddress.md)|Указывает на строку `BSTR`, инкапсулированную объектом `_bstr_t`.|
|[В формате BSTR](../cpp/bstr-t-getbstr.md)|Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.|
|[length](../cpp/bstr-t-length.md)|Возвращает число символов в объекте `_bstr_t`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[Оператор =](../cpp/bstr-t-operator-equal.md)|Присваивает новое значение существующему объекту `_bstr_t`.|
|[operator + =](../cpp/bstr-t-operator-add-equal-plus.md)|Добавляет символы в конец объекта `_bstr_t`.|
|[Оператор +](../cpp/bstr-t-operator-add-equal-plus.md)|Объединяет две строки.|
|[Оператор !](../cpp/bstr-t-operator-logical-not.md)|Проверяет, является ли инкапсулированный `BSTR` строкой со значением NULL.|
|[operator = =,! =, \<, >, \<=, > =](../cpp/bstr-t-relational-operators.md)|Сравнивает два объекта `_bstr_t`.|
|[Оператор wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md)|Извлекает указатели на инкапсулированный объект Юникода или многобайтовый объект `BSTR`.|

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:** \<комутил. h >

**Lib:** комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t является собственным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>См. также раздел

[Классы поддержки модели COM компилятора](../cpp/compiler-com-support-classes.md)
