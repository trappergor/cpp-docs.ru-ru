---
title: "Просмотр классов (архитектура) | Документы Microsoft"
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
- view classes [MFC]
- control views [MFC]
- view classes [MFC], architecture
ms.assetid: 8894579a-1436-441e-b985-83711061e495
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b2761253da0907b1736754068fa196dda361a8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="view-classes-architecture"></a>Классы представления (архитектура)
`CView`и его производные классы дочерних окон, которые представляют клиентской области окна фрейма. Представления отображают данные и принимать входные данные для документа.  
  
 Класс представления связан с классом документа и класс окна фрейма, используя объект шаблона документа.  
  
 [CView](../mfc/reference/cview-class.md)  
 Базовый класс для конкретного приложения представлений данных документа. Представления отображают данные и принимают пользовательский ввод, чтобы изменить или выбрать данные. Производные вашей представление классов из `CView`.  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 Базовый класс для представлений с возможностями прокрутки. Создайте производный класс представления из `CScrollView` для автоматической прокрутки.  
  
## <a name="form-and-record-views"></a>Формы и представления записей  
 Представления также прокрутки для представлений формы. Они основаны на шаблон диалогового окна.  
  
 Представления записей являются производными от представлений формы. Помимо шаблон диалогового окна они также имеют подключение к базе данных.  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 Представление прокрутки, макет которой определяется в шаблон диалогового окна. Производный класс `CFormView` для реализации пользовательского интерфейса, в зависимости от шаблона диалоговых окон.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Предоставляет форму непосредственно связана с объектом набора записей объекта доступа к данным (DAO). Все представления формы, например `CDaoRecordView` основан на шаблон диалогового окна.  
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 Поддерживает элемент управления для просмотра веб-страниц в приложении. Элемент управления поддерживает динамический HTML в MFC.  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 Обеспечивает поддержку MFC OLE DB для представлений формы.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Предоставляет форму непосредственно связана с объекта набора записей Open Database Connectivity (ODBC). Все представления формы, например `CRecordView` основан на шаблон диалогового окна.  
  
## <a name="control-views"></a>Элемент управления представления  
 Представления управления отображение элемента управления, как их представление.  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 Базовый класс для всех представлений, связанные с элементами управления Windows. Ниже описаны представления, основан на элементах управления.  
  
 [CEditView](../mfc/reference/ceditview-class.md)  
 Представление, содержащее Windows стандартный элемент управления (см. [CEdit](../mfc/reference/cedit-class.md)). Изменение элементов управления поддерживают редактирование текста, поиск, замена и возможностями прокрутки.  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Элемент управления редактирование представление, содержащее форматированный Windows (в разделе [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Помимо возможности элемента управления edit rich редактировать элементы управления поддержки шрифты, цвета, форматирование абзаца и внедренные объекты OLE.  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Представление, содержащее список элемента управления Windows (в разделе [CListCtrl](../mfc/reference/clistctrl-class.md)). Элемент управления списка отображаются значки и строки так же, как на правую панель проводника.  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Представление, содержащее дерево элемента управления Windows (в разделе [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Структура дерева отображаются значки и строки, иерархически так же, как к левой панели проводника.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

