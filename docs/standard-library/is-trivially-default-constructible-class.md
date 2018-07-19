---
title: Класс is_trivially_default_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa7b831790804005f0649dbae0dbb98df5121106
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954738"
---
# <a name="istriviallydefaultconstructible-class"></a>Класс is_trivially_default_constructible

Проверяет, есть ли у типа тривиальный конструктор по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Параметры

*Ty* запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим тривиальный конструктор, в противном случае он содержит значение false.

Конструктор по умолчанию для класса *Ty* является тривиальным если:

- он является конструктором по умолчанию, объявленным неявно;

- Класс *Ty* не имеет виртуальных функций

- Класс *Ty* не имеет виртуальных баз

- все прямые базы класса *Ty* имеют тривиальные конструкторы

- классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы;

- классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
