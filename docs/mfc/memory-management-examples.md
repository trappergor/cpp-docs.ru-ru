---
title: "Управление памятью. Примеры | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], выделение ресурсов"
  - "массивы [C++], управление памятью"
  - "структуры данных [C++]"
  - "структуры данных [C++], выделение памяти"
  - "примеры [MFC], выделение памяти"
  - "выделение кадров"
  - "выделение кучи, примеры"
  - "выделение памяти [C++], массивы"
  - "выделение памяти [C++], структуры данных"
  - "выделение памяти [C++], примеры"
  - "выделение памяти [C++], объекты"
  - "MFC [C++], управление памятью"
  - "объекты [C++], выделение памяти"
  - "объекты [C++], выделение памяти"
  - "выделение памяти структуры"
  - "типы [C++], выделение памяти"
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Управление памятью. Примеры
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются как MFC выполняет выделения кадра и выделения памяти для каждого из 3 типичных выделения памяти:  
  
-   [Массив байтов](#_core_allocation_of_an_array_of_bytes)  
  
-   [Структура данных](#_core_allocation_of_a_data_structure)  
  
-   [Объект](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> Выделение массива байтов  
  
#### Выбор массив байтов в кадре  
  
1.  Определите массив, как показано в следующем коде.  Массив автоматически удаляется, и его освобождение памяти, если переменная массива не влияет на ее область.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/CPP/memory-management-examples_1.cpp)]  
  
#### Выбор массив байтов \(или любой примитивный тип данных в куче\)  
  
1.  Оператор **новый** с синтаксисом массива, показанный в следующем примере:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/CPP/memory-management-examples_2.cpp)]  
  
#### Отменить массивы из кучи  
  
1.  Оператор **удалить** следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/CPP/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> Выделение структуры данных  
  
#### Выбор структуры данных в кадре  
  
1.  Определите переменную структуры следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/CPP/memory-management-examples_4.cpp)]  
  
     Память занятая структурой фиксируется при ее не влияет на ее область.  
  
#### Выбор структуры данных в куче  
  
1.  Используйте **новый** для выделения структуры данных в куче и **удалить**, чтобы отменить их, как показано в следующих примерах:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/CPP/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> Выделение объектов  
  
#### Выберите объект в кадре  
  
1.  Объявите объект следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/CPP/memory-management-examples_6.cpp)]  
  
     Деструктор для объекта автоматически вызывается, когда объект покидает его области.  
  
#### Выбор объекта в куче  
  
1.  Оператор **новый**, который возвращает указатель на объект, чтобы выделить объекты в куче.  Оператор **удалить** для удаления их.  
  
     В следующих примерах кучи и кадра высказывать конструктор `CPerson` не принимает аргументов.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/CPP/memory-management-examples_7.cpp)]  
  
     Если аргумент для конструктора `CPerson` указатель на `char`, выписка для выделения кадра выглядит следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/CPP/memory-management-examples_8.cpp)]  
  
     Выписка для выделения кучи выглядит следующим образом:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/CPP/memory-management-examples_9.cpp)]  
  
## См. также  
 [Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)