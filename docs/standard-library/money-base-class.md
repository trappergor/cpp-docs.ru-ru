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
ms.openlocfilehash: 805045e4ea63f153e9a35b0d4b068bd69874b93f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864090"
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

Перечисление **часть** описывает возможные значения в элементах поля массива в шаблоне структуры. Значения **часть**:

- **none** для соответствия нулю или более пробелам или для формирования пустого значения.

- **sign** для соответствия или формирования знака плюс или минус.

- **space** для соответствия нулю или более пробелам или для формирования пробела.

- **symbol** для соответствия или формирования символа валюты.

- **value** для соответствия или формирования денежного значения.

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
