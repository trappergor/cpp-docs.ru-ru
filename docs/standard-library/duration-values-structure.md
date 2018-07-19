---
title: Структура duration_values | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d781d04097b205750e7ac65529cfa8ad7b37f9c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846016"
---
# <a name="durationvalues-structure"></a>Структура duration_values

Предоставляет конкретные значения для параметра-шаблона [длительности](../standard-library/duration-class.md) `Rep`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[max](#max)|Статический. Указывает верхний предел для значения типа `Rep`.|
|[min](#min)|Статический. Указывает нижний предел для значения типа `Rep`.|
|[Ноль](#zero)|Статический. Возвращает `Rep(0)`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="max"></a>  duration_values::max

Статический метод, который возвращает верхнюю границу значений типа `Ref`.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `numeric_limits<Rep>::max()`.

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно быть больше [duration_values::zero](#zero).

## <a name="min"></a>  duration_values::min

Статический метод, который возвращает нижнюю границу для значений типа `Ref`.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `numeric_limits<Rep>::lowest()`.

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно быть меньше или равно [duration_values::zero](#zero).

## <a name="zero"></a>  duration_values::zero

Возвращает `Rep(0)`.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Примечания

Если `Rep` является пользовательским типом, возвращаемое значение должно представлять аддитивную бесконечность.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
