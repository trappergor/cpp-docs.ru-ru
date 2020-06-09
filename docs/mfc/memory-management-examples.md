---
title: Управление памятью. Примеры
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
ms.openlocfilehash: ca5056303f77f112e18ef09d606789a5b1c92acd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626314"
---
# <a name="memory-management-examples"></a>Управление памятью. Примеры

В этой статье описывается, как MFC выполняет выделение кадров и выделение кучи для каждого из трех типичных типов выделения памяти:

- [Массив байтов](#_core_allocation_of_an_array_of_bytes)

- [Структура данных](#_core_allocation_of_a_data_structure)

- [Объект](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a>Выделение массива байтов

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Выделение массива байтов в кадре

1. Определите массив, как показано в следующем коде. Массив автоматически удаляется и его память освобождается, когда переменная массива выходит из области действия.

   [!code-cpp[NVC_MFC_Utilities#1](codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Выделение массива байтов (или любого типа данных-примитива) в куче

1. Используйте оператор **New** с синтаксисом массива, показанным в этом примере:

   [!code-cpp[NVC_MFC_Utilities#2](codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Освобождение массивов из кучи

1. Используйте оператор **Delete** следующим образом:

   [!code-cpp[NVC_MFC_Utilities#3](codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a>Выделение структуры данных

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Выделение структуры данных в кадре

1. Определите переменную структуры следующим образом:

   [!code-cpp[NVC_MFC_Utilities#4](codesnippet/cpp/memory-management-examples_4.cpp)]

   Память, занятая структурой, освобождается при выходе из нее области.

#### <a name="to-allocate-data-structures-on-the-heap"></a>Распределение структур данных в куче

1. Используйте **New** для выделения структур данных в куче и **удаления** , чтобы освободить их, как показано в следующих примерах:

   [!code-cpp[NVC_MFC_Utilities#5](codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a>Выделение объекта

#### <a name="to-allocate-an-object-on-the-frame"></a>Выделение объекта в кадре

1. Объявите объект следующим образом:

   [!code-cpp[NVC_MFC_Utilities#6](codesnippet/cpp/memory-management-examples_6.cpp)]

   Деструктор объекта автоматически вызывается при выходе объекта из области действия.

#### <a name="to-allocate-an-object-on-the-heap"></a>Выделение объекта в куче

1. Используйте оператор **New** , который возвращает указатель на объект, чтобы выделить объекты в куче. Удалите их с помощью оператора **Delete** .

   В следующей куче и примерах с кадрами предполагается, что `CPerson` конструктор не принимает аргументов.

   [!code-cpp[NVC_MFC_Utilities#7](codesnippet/cpp/memory-management-examples_7.cpp)]

   Если аргумент для `CPerson` конструктора является указателем на **char**, инструкция для выделения фрейма имеет вид:

   [!code-cpp[NVC_MFC_Utilities#8](codesnippet/cpp/memory-management-examples_8.cpp)]

   Инструкция для выделения кучи:

   [!code-cpp[NVC_MFC_Utilities#9](codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>См. также раздел

[Управление памятью. Выделение кучи](memory-management-heap-allocation.md)
