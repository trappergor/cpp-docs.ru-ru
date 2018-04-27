---
title: '&lt;queue&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <queue>
dev_langs:
- C++
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3bccad1ff20a314c562b580d4d5102f283bcef56
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltqueuegt"></a>&lt;queue&gt;

Определяет классы шаблонов priority_queue и очереди, а также несколько вспомогательных шаблонов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <queue>

```

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор!=](../standard-library/queue-operators.md#op_neq)|Проверяет неравенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор<](../standard-library/queue-operators.md#op_lt)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, меньше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|
|[оператор==](../standard-library/queue-operators.md#op_eq_eq)|Проверяет равенство объекта queue слева от оператора объекту queue справа от оператора.|
|[оператор>](../standard-library/queue-operators.md#op_gt)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора.|
|[оператор>=](../standard-library/queue-operators.md#op_gt_eq)|Проверяет, больше ли объект queue слева от оператора, чем объект queue справа от оператора, или равен ему.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс queue](../standard-library/queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к переднему и заднему элементам некоторого базового типа контейнера.|
|[Класс priority_queue](../standard-library/priority-queue-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к верхнему элементу некоторого базового типа контейнера, который всегда является самым большим.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
