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
ms.openlocfilehash: f521681da10eeda3b8024b0865d5164021296353
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838715"
---
# <a name="_bstr_t-class"></a>Класс _bstr_t

**Блок, относящийся только к системам Microsoft**

`_bstr_t`Объект инкапсулирует [тип данных BSTR](/previous-versions/windows/desktop/automat/bstr). Класс управляет выделением и освобождением ресурсов с помощью вызовов функций `SysAllocString` и `SysFreeString` других `BSTR` API, если это уместно. Класс **_bstr_t** использует подсчет ссылок во избежание чрезмерных издержек.

### <a name="construction"></a>Строительство

| Конструктор | Описание |
|--|--|
| [_bstr_t](../cpp/bstr-t-bstr-t.md) | Формирует объект `_bstr_t`. |

### <a name="operations"></a>Operations

| Функция | Описание |
|--|--|
| [Assign](../cpp/bstr-t-assign.md) | Копирует строку `BSTR` в строку `BSTR`, инкапсулированную объектом `_bstr_t`. |
| [Attach](../cpp/bstr-t-attach.md) | Связывает упаковщик `_bstr_t` со строкой `BSTR`. |
| [copy](../cpp/bstr-t-copy.md) | Создает копию инкапсулированного объекта `BSTR`. |
| [Отсоединить](../cpp/bstr-t-detach.md) | Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`). |
| [GetAddress](../cpp/bstr-t-getaddress.md) | Указывает на строку `BSTR`, инкапсулированную объектом `_bstr_t`. |
| [GetBSTR](../cpp/bstr-t-getbstr.md) | Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`. |
| [length](../cpp/bstr-t-length.md) | Возвращает число символов в объекте `_bstr_t`. |

### <a name="operators"></a>Операторы

| Оператор | Описание |
|--|--|
| [Оператор =](../cpp/bstr-t-operator-equal.md) | Присваивает новое значение существующему объекту `_bstr_t`. |
| [operator + =](../cpp/bstr-t-operator-add-equal-plus.md) | Добавляет символы в конец объекта `_bstr_t`. |
| [operator +](../cpp/bstr-t-operator-add-equal-plus.md) | Объединяет две строки. |
| [станции!](../cpp/bstr-t-operator-logical-not.md) | Проверяет, является ли Инкапсулированная `BSTR` строка пустой. |
| [operator = =,! =, \<, > , \<=, >=](../cpp/bstr-t-relational-operators.md) | Сравнивает два объекта `_bstr_t`. |
| [Оператор wchar_t * &#124; char\*](../cpp/bstr-t-wchar-t-star-bstr-t-char-star.md) | Извлекает указатели на инкапсулированный объект Юникода или многобайтовый объект `BSTR`. |

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="requirements"></a>Требования

**Заголовок:**\<comutil.h>

**Lib:** комсуппв. lib или комсуппвд. lib (Дополнительные сведения см. в разделе [/Zc: wchar_t (wchar_t является собственным типом)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>См. также раздел

[Классы поддержки COM компилятора](../cpp/compiler-com-support-classes.md)
