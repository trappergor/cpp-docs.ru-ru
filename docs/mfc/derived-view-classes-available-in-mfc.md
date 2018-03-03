---
title: "Производные классы представлений, доступные в MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2426f3e547da6eaab6a4b38bb5199e87c93ef933
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="derived-view-classes-available-in-mfc"></a>Производные классы представлений, доступные в MFC
Следующая таблица показывает представление классы MFC и их связи друг с другом. Возможности класса представления, зависят от класс представления MFC, из которого он является производным.  
  
### <a name="view-classes"></a>Классы представлений  
  
|Класс|Описание:|  
|-----------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|Базовый класс для всех представлений.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Базовый класс `CTreeView`, `CListView`, `CEditView`, и `CRichEditView`. Эти классы позволяют использовать архитектуры document/view с указанных общих элементов управления Windows.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Поле поля ввода простого представления на базе ОС Windows. Позволяет вводить и изменять текст и может использоваться в качестве основы для приложение простого текстового редактора. См. также раздел `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|В представление, содержащее [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) объекта. Этот класс является аналогом `CEditView`, но в отличие от `CEditView`, `CRichEditView` дескрипторы форматированный текст.|  
|[CListView](../mfc/reference/clistview-class.md)|В представление, содержащее [CListCtrl](../mfc/reference/clistctrl-class.md) объекта.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|В представление, содержащее [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объекта для представлений, которые похожи на окне обозревателя решений в Visual C++.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Базовый класс `CFormView`, `CRecordView`, и `CDaoRecordView`. Реализует прокрутки просмотреть содержимое.|  
|[CFormView](../mfc/reference/cformview-class.md)|Представление формы, представление, содержащее элементы управления. Приложения на основе форм предоставляет один или несколько таких интерфейсов формы.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Веб-представление браузера, с которым пользователь приложения может просматривать сайты в Интернете, а также папки в локальной файловой системе и в сети. Веб-представление браузера также можно работать как контейнер активного документа.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|Представление формы, которое отображает записи базы данных ODBC в элементах управления. Если выбрана поддержка ODBC в проекте, базовый класс представления является `CRecordView`. Представление подключен к `CRowset` объекта.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Представление формы, которое отображает записи базы данных DAO в элементах управления. При выборе DAO поддержки в вашем проекте базовый класс представления является `CDaoRecordView`. Представление подключен к `CDaoRecordset` объекта.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Представление формы, которое отображает записи OLE DB в элементах управления. При выборе поддержки OLE DB в проекте базовый класс представления является `COleDBRecordView`. Представление подключен к `CRowset` объекта.|  
  
> [!NOTE]
>  Начиная с версии 4.0, MFC `CEditView` является производным от `CCtrlView`.  
  
 Для использования этих классов в приложении, от них происходят классов представления приложения. Дополнительные сведения см. в разделе [прокрутка и масштабирование представления](../mfc/scrolling-and-scaling-views.md). Дополнительные сведения о классах баз данных см. в разделе [Обзор: программирования баз данных](../data/data-access-programming-mfc-atl.md).  
  
## <a name="see-also"></a>См. также  
 [Использование представлений](../mfc/using-views.md)

