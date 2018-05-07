---
title: '&lt;tuple&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <tuple>
dev_langs:
- C++
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f21988d65374149b771f32c553157b37a0578851
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Определяет шаблон `tuple`, экземпляры которого содержат объекты различных типов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <tuple>
```

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[tuple](../standard-library/tuple-class.md)|Создает последовательность элементов фиксированной длины.|
|[Класс tuple_element](../standard-library/tuple-element-class-tuple.md)|Заключает в оболочку тип элемента `tuple`.|
|[Класс tuple_size](../standard-library/tuple-size-class-tuple.md)|Создает оболочку для счетчика элементов `tuple`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор==](../standard-library/tuple-operators.md#op_eq_eq)|Сравнение объектов `tuple`, равенство|
|[оператор!=](../standard-library/tuple-operators.md#op_neq)|Сравнение объектов `tuple`, неравенство|
|[оператор<](../standard-library/tuple-operators.md#op_lt)|Сравнение объектов `tuple`, меньше|
|[оператор<=](../standard-library/tuple-operators.md#op_lt_eq)|Сравнение объектов `tuple`, меньше или равно|
|[оператор>](../standard-library/tuple-operators.md#op_gt)|Сравнение объектов `tuple`, больше|
|[оператор>=](../standard-library/tuple-operators.md#op_gt_eq)|Сравнение объектов `tuple`, больше или равно|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|Возвращает элемент из объекта `tuple`.|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Создает `tuple` из значений элементов.|
|[tie](../standard-library/tuple-functions.md#tie)|Создает `tuple` из ссылок на элементы.|

## <a name="see-also"></a>См. также

[\<array>](../standard-library/array.md)<br/>
