---
title: Класс money_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3195d2c988abcfb2d62acb4ece957c8c5156bbd7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965692"
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
