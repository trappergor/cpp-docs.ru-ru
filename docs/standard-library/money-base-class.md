---
title: Класс money_base
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: b0c77b523dbe31bc5b07ae3d736441880fe04546
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610456"
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

Перечисление `part` описывает возможные значения в элементах поля массива в шаблоне структуры. Значения `part` являются:

- `none` для соответствия нулю или более пробелам или формирования пустого значения.

- `sign` для соответствия или формирования положительный или отрицательный знак.

- `space` для соответствия нулю или более пробелам или для формирования пробела.

- `symbol` для соответствия или формирования символа валюты.

- `value` для соответствия или формирования денежного значения.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
