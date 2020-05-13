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
ms.openlocfilehash: 3a1e647175b7b5294e672efbf234e3ae2853e411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367850"
---
# <a name="memory-management-examples"></a>Управление памятью. Примеры

В этой статье описывается, как MFC выполняет распределение кадров и кучи для каждого из трех типичных видов распределения памяти:

- [Массив байтов](#_core_allocation_of_an_array_of_bytes)

- [Структура данных](#_core_allocation_of_a_data_structure)

- [Объект](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a>Распределение массива байтов

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Распределить массив байтов на раме

1. Определите массив, показанный следующим кодом. Массив автоматически удаляется и его память удаляется, когда переменная массива выходит из своей области.

   [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Для выделения массива байтов (или любого примитивного типа данных) на куче

1. Используйте **нового** оператора с синтаксисом массива, показанным в этом примере:

   [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Чтобы распределить массивы из кучи

1. Используйте оператора **удаления** следующим образом:

   [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a>Распределение структуры данных

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Распределение структуры данных на кадре

1. Определите переменную структуры следующим образом:

   [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]

   Память, занимаемая структурой, рекультивируется при выходе из сферы.

#### <a name="to-allocate-data-structures-on-the-heap"></a>Распределение структур данных на куче

1. Используйте **новые** для распределения структур данных на куче и **удаления,** чтобы распределить их, как показано на следующих примерах:

   [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a>Распределение объекта

#### <a name="to-allocate-an-object-on-the-frame"></a>Для выделения объекта на раме

1. Объявить объект следующим образом:

   [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]

   Деструктор объекта автоматически вызывается при выходе объекта из сферы действия объекта.

#### <a name="to-allocate-an-object-on-the-heap"></a>Для выделения объекта на куче

1. Используйте **новый** оператор, который возвращает указатель объекту, чтобы выделить объекты на куче. Используйте оператора **удаления,** чтобы удалить их.

   Следующие примеры кучи и `CPerson` кадры предполагают, что конструктор не принимает никаких аргументов.

   [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]

   Если аргументом `CPerson` в пользу конструктора является указатель для **символа,** выписка для распределения кадров:

   [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]

   Заявление о распределении кучи:

   [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>См. также раздел

[Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)
