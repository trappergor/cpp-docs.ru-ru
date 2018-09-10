---
title: Класс is_trivially_copy_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1924b82f7c3035ea2aecb463199558c9ead45c91
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102069"
---
# <a name="istriviallycopyconstructible-class"></a>Класс is_trivially_copy_constructible

Проверяет, есть ли у типа тривиальный конструктор копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является классом, имеющим тривиальный конструктор копии, в противном случае он содержит значение false.

Конструктор копии для класса *T* является тривиальным, если он неявно объявляется, класс *T* не имеет виртуальных функций или виртуальных базовых классов, все прямые базовые классы класса *T* имеют тривиальные конструкторы копирования; классы всех нестатических членов типа класса имеют тривиальные конструкторы копий и классы всех нестатических членов массива типов класса имеют тривиальные конструкторы копирования.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
