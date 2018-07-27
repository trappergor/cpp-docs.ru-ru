---
title: 'Управление памятью: Примеры | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21efd095a1d8e89c140ef39072a753c300a3043b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929311"
---
# <a name="memory-management-examples"></a>Управление памятью. Примеры
Этой статье описывается, как MFC выполняет рамки выделения и выделения кучи для каждого из трех типичных операций выделения памяти.  
  
-   [Массив байтов](#_core_allocation_of_an_array_of_bytes)  
  
-   [Структура данных](#_core_allocation_of_a_data_structure)  
  
-   [Объект](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Выделение массива байтов  
  
#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Чтобы выделить память для массива байтов в кадре  
  
1.  Определите массив, как показано в следующем примере кода. Автоматически удаляется массива и освобождения памяти, завершая ее область действия переменной массива.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]  
  
#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Чтобы выделить память для массива байт (или любой тип-примитив) в куче  
  
1.  Используйте **новый** оператор с синтаксисом массива, показано в следующем примере:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]  
  
#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Для освобождения массивов из кучи  
  
1.  Используйте **удалить** оператор следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Выделение структуры данных  
  
#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Чтобы выделить структуру данных в кадре  
  
1.  Задайте переменную структуры следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]  
  
     Память, занятую структура будет удален при выходе его области.  
  
#### <a name="to-allocate-data-structures-on-the-heap"></a>Для выделения структуры данных в куче  
  
1.  Используйте **новый** для выделения структуры данных в куче и **удаление** для освобождения их, как показано в следующих примерах:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> Размещение объекта  
  
#### <a name="to-allocate-an-object-on-the-frame"></a>Чтобы выделить объект в кадре  
  
1.  Объявите объект следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]  
  
     Деструктор для объекта вызывается автоматически, когда объект выходит из области.  
  
#### <a name="to-allocate-an-object-on-the-heap"></a>Для выделения объекта в куче  
  
1.  Используйте **новый** оператор, который возвращает указатель на объект, для выделения объектов в куче. Используйте **удалить** оператор для их удаления.  
  
     В следующих примерах кучи и кадра предполагается, что `CPerson` конструктор без аргументов.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]  
  
     Если аргумент для `CPerson` конструктор является указателем на **char**, инструкция для выделение кадров:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]  
  
     Инструкция для выделения кучи является:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)

