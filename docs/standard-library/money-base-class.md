---
title: Класс money_base
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 5b19635cf4d2cce58ec50226c463a075cfac5b0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455564"
---
# <a name="moneybase-class"></a>Класс money_base

Данный класс описывает перечисление и структуру, общие для всех специализаций класса-шаблона [moneypunct](../standard-library/moneypunct-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Примечания

Перечисление `part` описывает возможные значения в элементах поля массива в шаблоне структуры. Значения `part` :

- `none`значение, чтобы сопоставить ноль или больше пробелов или ничего не создавать.

- `sign`для сопоставления или создания положительного или отрицательного знака.

- `space`значение, чтобы сопоставить ноль или больше пробелов или сгенерировать пробел.

- `symbol`для сопоставления или создания символа валюты.

- `value`для сопоставления или создания денежного значения.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
