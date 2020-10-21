---
title: Функции &lt;random&gt;
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 3d94f607fc6b7bdf22d7f573f590b451dbaa718d
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274603"
---
# <a name="ltrandomgt-functions"></a>Функции &lt;random&gt;

## <a name="generate_canonical"></a><a name="generate_canonical"></a> generate_canonical

Возвращает значение с плавающей запятой из случайной последовательности.

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>Параметры

*реалтипе*\
Тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md) .

*Числа*\
Количество используемых битов случайности.

*Формирования*\
Класс генератора случайных чисел.

*Операций*\
Ссылка на экземпляр генератора случайных чисел типа " *генератор*".

### <a name="remarks"></a>Remarks

Функция шаблона вызывает `operator()` многократное *Gen* обращение и упаковывает возвращаемые значения в значение с плавающей запятой `x` типа *реалтипе* до тех пор, пока не собрало указанное число битов мантиссаа в `x` . Указанное число является меньшим из *битов* (значение которого должно быть ненулевым) и полным числом битов мантисса в *реалтипе*. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.
