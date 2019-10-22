---
title: Класс money_base
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: c614832b0cbb1cc23e42ecb3a939ccf1334a5cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689323"
---
# <a name="money_base-class"></a>Класс money_base

Класс описывает перечисление и структуру, общую для всех специализаций шаблона класса [moneypunct](../standard-library/moneypunct-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Заметки

Перечисление `part` описывает возможные значения в элементах поля массива в шаблоне структуры. Значения `part`:

- `none`, чтобы сопоставить ноль или больше пробелов или ничего не создавать.

- `sign` для сопоставления или создания положительного или отрицательного знака.

- `space` для сопоставления нуля или более пробелов или создания пробела.

- `symbol` для сопоставления или создания символа валюты.

- `value` для сопоставления или создания денежного значения.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
