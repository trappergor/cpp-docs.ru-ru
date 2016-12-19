---
title: "Производные классы представлений, доступные в MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы [C++], производные"
  - "CView - класс, класс является производным от"
  - "производные классы, классы представлений"
  - "классы представлений, производные"
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Производные классы представлений, доступные в MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующей таблице приведены классы представлений MFC и их связи друг с другим.  Возможности класса представления зависят от класса представлений MFC, из которого он наследуется.  
  
### Классы представления  
  
|Класс|Описание|  
|-----------|--------------|  
|[CView](../Topic/CView%20Class.md)|Базовым классом для всех представлений.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Базовый класс `CTreeView`, `CListView`, `CEditView` и `CRichEditView`.  Эти классы позволяют использовать архитектуры документов и представлений, представленные с общими элементами управления Windows.|  
|[CEditView](../Topic/CEditView%20Class.md)|Простое представление, основанное на элементе управления поля ввода Windows.  Позволяет вставлять и изменять текст и может использоваться в качестве основы для простого приложения текстового редактора.  См. также раздел `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Представление, содержащее объект [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md).  Этот класс аналогичн в `CEditView`, но в отличие от `CEditView`, форматированный текст на `CRichEditView`.|  
|[CListView](../mfc/reference/clistview-class.md)|Представление, содержащее объект [CListCtrl](../Topic/CListCtrl%20Class.md).|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Представление, содержащее объект [CTreeCtrl](../mfc/reference/ctreectrl-class.md), для представлений, которые похожи на окно обозревателя решений в Visual C\+\+.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Базовый класс `CFormView`, `CRecordView` и `CDaoRecordView`.  Реализует прокручивать содержимое представления.|  
|[CFormView](../mfc/reference/cformview-class.md)|Представление формы, представление, содержащее элементы управления.  Приложение на основе предоставляет одну или несколько такие интерфейсы формы.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Представление веб\-браузера, с которым пользователь приложения может просматривать сайты в Интернете, так и папки в локальной файловой системе и в сети.  Представление веб\-браузера также может служить контейнер активных документов.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|Представление формы, записи базы данных ODBC отображаются в элементах управления.  Если вы выбираете проект поддержка ODBC в проекте, базовый класс представления `CRecordView`.  Представление подключение к объекту `CRowset`.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Представление формы, записи базы данных DAO отображаются в элементах управления.  Если вы выбираете проект поддержка DAO в проекте, базовый класс представления `CDaoRecordView`.  Представление подключение к объекту `CDaoRecordset`.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Представление формы, записи OLE DB отображаются в элементах управления.  Если вы выбираете проект поддержка OLE DB в проекте, базовый класс представления `COleDBRecordView`.  Представление подключение к объекту `CRowset`.|  
  
> [!NOTE]
>  Начиная с версии MFC 4.0, `CEditView` является производным от `CCtrlView`.  
  
 Для использования этих классов в приложении производные классы представления приложения от них.  Дополнительные сведения см. в разделе [Прокрутка и масштабирования представления](../mfc/scrolling-and-scaling-views.md).  Дополнительные сведения о классах баз данных см. в разделе [Общие сведения: Программирование базы данных](../data/data-access-programming-mfc-atl.md).  
  
## См. также  
 [Использование представлений](../mfc/using-views.md)