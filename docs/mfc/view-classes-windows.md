---
title: "Просмотр классов (Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.view
dev_langs:
- C++
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3d737176df2676f543f47bb77a0d205fa7c908fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="view-classes-windows"></a>Классы представления (Windows)
`CView`и его производные классы дочерних окон, которые представляют клиентской области окна фрейма. Представления отображают данные и принимать входные данные для документа.  
  
 Класс представления связан с классом документа и класс окна фрейма, используя объект шаблона документа.  
  
 [CView](../mfc/reference/cview-class.md)  
 Базовый класс для конкретного приложения представлений данных документа. Представления отображают данные и принимают пользовательский ввод, чтобы изменить или выбрать данные. Является производным класса представления или классы из `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Базовый класс для представлений с возможностями прокрутки. Создайте производный класс представления из `CScrollView` для автоматической прокрутки.  
  
## <a name="form-and-record-views"></a>Формы и представления записей  
 Представления также прокрутки для представлений формы. Они основаны на шаблон диалогового окна.  
  
 Представления записей являются производными от представлений формы. Помимо шаблон диалогового окна они также имеют подключение к базе данных.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Представление прокрутки, макет которой определяется в шаблон диалогового окна. Производный класс `CFormView` для реализации пользовательского интерфейса, в зависимости от шаблона диалоговых окон.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Предоставляет форму непосредственно связана с объектом набора записей объекта доступа к данным (DAO). Все представления формы, например `CDaoRecordView` основан на шаблон диалогового окна.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Предоставляет форму непосредственно связана с объекта набора записей Open Database Connectivity (ODBC). Все представления формы, например `CRecordView` основан на шаблон диалогового окна.  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 Представление формы, которая предоставляет функции платформы редактирования WebBrowser HTML.  
  
## <a name="control-views"></a>Элемент управления представления  
 Представления управления отображение элемента управления, как их представление.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Базовый класс для всех представлений, связанные с элементами управления Windows. Ниже описаны представления, основан на элементах управления.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Представление, содержащее Windows стандартный элемент управления (см. [CEdit](../mfc/reference/cedit-class.md)). Изменение элементов управления поддерживают редактирование текста, поиск, замена и возможностями прокрутки.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Элемент управления редактирование представление, содержащее форматированный Windows (в разделе [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Помимо возможности элемента управления edit rich редактировать элементы управления поддержки шрифты, цвета, форматирование абзаца и внедренные объекты OLE.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Представление, содержащее список элемента управления Windows (в разделе [CListCtrl](../mfc/reference/clistctrl-class.md)). Элемент управления списком отображает коллекцию элементов, каждый элемент состоит из значка и метки, так же, как на правую панель проводника.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Представление, содержащее дерево элемента управления Windows (в разделе [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Дерево отображает иерархический список значков и метки организованы так же, как к левой панели проводника.  
  
## <a name="related-classes"></a>Связанные классы  
 `CSplitterWnd`можно иметь несколько представлений в одном окне фрейма. `CPrintDialog`и `CPrintInfo` поддерживают возможность печати и предварительного просмотра представлений. `CRichEditDoc`и `CRichEditCntrItem` используются с `CRichEditView` для реализации возможностей контейнера OLE.  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 Окно, которое пользователь может разбить на несколько областей. Эти области могут быть пользователем или фиксированного размера с раскрывающимися списками.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Предоставляет стандартное диалоговое окно для печати файла.  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 Структура, содержащая сведения о задании печати или предварительного просмотра. Используемые `CView`печати архитектуры.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Ведет список клиентских элементов управления OLE, которые находятся в `CRichEditView`.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Предоставляет клиентский доступ к объект OLE, хранимый в `CRichEditView`.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

