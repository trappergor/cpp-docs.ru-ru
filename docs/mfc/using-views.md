---
title: "Использование представлений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99493657313d480559d232bf9033dfb7a7a585c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-views"></a>Использование представлений
Просмотр ответственности — для графического отображения данных документа пользователю принять и интерпретировать ввод данных пользователем как операций над документом. — Задач в классе представления записи.  
  
-   Написать класс представления [OnDraw](../mfc/reference/cview-class.md#ondraw) функция-член, который отображает данные документа.  
  
-   Функции-члены обработчика сообщений в классе представления подключиться соответствующих сообщений Windows и объекты пользовательского интерфейса, например пунктах меню.  
  
-   Реализуйте эти обработчики для интерпретации ввод данных пользователем.  
  
 Кроме того, необходимо переопределить других `CView` функции-члены в класс производным представлением. В частности, может потребоваться переопределить [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) для выполнения специальных инициализации для представления и [OnUpdate](../mfc/reference/cview-class.md#onupdate) для выполнения специальной обработки требуется непосредственно перед перерисовывается представления. Для многостраничных документов, необходимо также переопределить [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) инициализировать диалоговое окно печати с числом печатаемых страниц и другие сведения. Дополнительные сведения о переопределении `CView` функции-члены, см. класс [CView](../mfc/reference/cview-class.md) в *Справочник по библиотеке MFC*.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Производные классы представлений доступные в MFC](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Рисование в представлении](../mfc/drawing-in-a-view.md)  
  
-   [Интерпретация ввода пользователя через представление](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Роль просмотра при печати](../mfc/role-of-the-view-in-printing.md)  
  
-   [Масштаба и прокрутка представлений](../mfc/scrolling-and-scaling-views.md)  
  
-   [Инициализация и очистка документов и представлений](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>См. также  
 [Архитектура документа/обзора](../mfc/document-view-architecture.md)   
 [Класс CFormView](../mfc/reference/cformview-class.md)   
 [Представления записей (доступ к данным MFC)](../data/record-views-mfc-data-access.md)   
 [Обход механизма сериализации](../mfc/bypassing-the-serialization-mechanism.md)

