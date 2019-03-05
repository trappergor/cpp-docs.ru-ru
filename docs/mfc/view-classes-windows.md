---
title: Классы представления (Windows)
ms.date: 11/04/2016
f1_keywords:
- vc.classes.view
helpviewer_keywords:
- form and record views [MFC]
- splitter window classes [MFC]
- view classes [MFC], Windows
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
ms.openlocfilehash: ad58fd6fa2548c2cf320baf75b8fc33a835ddd55
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267099"
---
# <a name="view-classes-windows"></a>Классы представления (Windows)

`CView` и его производные классы являются дочерними окнами, которые представляют клиентской области окна фрейма. Представления отображают данные и принимать входные данные для документа.

Класс представления, связанный с класса документов и класс окна фрейма, используя объект шаблона документа.

[CView](../mfc/reference/cview-class.md)<br/>
Базовый класс для конкретных представлений данных документа. Представления отображают данные и принимают пользовательский ввод, чтобы изменить или выберите данные. Производные представления класса или классов из `CView`.

[CScrollView](../mfc/reference/cscrollview-class.md)<br/>
Базовый класс для представлений с возможностями прокрутки. Наследование класса из представления `CScrollView` для автоматической прокрутки.

## <a name="form-and-record-views"></a>Формы и представления записей

Представления также прокрутки для представлений формы. Они основаны на шаблон диалогового окна.

Представления записей являются производными от представления форм. Помимо шаблон диалогового окна они также иметь подключение к базе данных.

[CFormView](../mfc/reference/cformview-class.md)<br/>
Представление прокрутки, макет которой определяется в шаблон диалогового окна. Наследуйте класс от `CFormView` для реализации пользовательского интерфейса, в зависимости от шаблона диалогового окна.

[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)<br/>
Предоставляет форму непосредственно связана с объектом набора записей объекта доступа к данным (DAO). Все представления формы, такие как `CDaoRecordView` основан на шаблон диалогового окна.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Предоставляет форму непосредственно связана с объект recordset Open Database Connectivity (ODBC). Все представления формы, такие как `CRecordView` основан на шаблон диалогового окна.

[CHtmlEditView](../mfc/reference/chtmleditview-class.md)<br/>
Представление формы, которая предоставляет функции платформы редактирования WebBrowser HTML.

## <a name="control-views"></a>Представления элементов управления

Представления управления отображение элемента управления, как их представление.

[CCtrlView](../mfc/reference/cctrlview-class.md)<br/>
Базовый класс для всех представлений, связанных с элементами управления Windows. Ниже приведено описание представления, основанные на элементы управления.

[CEditView](../mfc/reference/ceditview-class.md)<br/>
Представление, содержащее Windows стандартный элемент управления (см. в разделе [CEdit](../mfc/reference/cedit-class.md)). Изменение текста поддержки элементов управления при редактировании, поиск, замена и возможностями прокрутки.

[CRichEditView](../mfc/reference/cricheditview-class.md)<br/>
Представление, содержащее Windows широкими возможностями редактирования (см. в разделе [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Помимо возможностей элемента управления edit ввод с форматированием шрифтов поддержка элементов управления, цвета, форматирование абзацев и внедренные объекты OLE.

[CListView](../mfc/reference/clistview-class.md)<br/>
Представление, содержащее элемент управления списка Windows (см. в разделе [CListCtrl](../mfc/reference/clistctrl-class.md)). Элемент управления списка отображает коллекцию элементов, каждый элемент состоит из значок и метку, так же, как на правую панель проводника.

[CTreeView](../mfc/reference/ctreeview-class.md)<br/>
Представление, содержащее древовидным элементом управления Windows (см. в разделе [CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Дерево отображает иерархический список значкам и меткам, расположенные в так же, как к левой панели проводника.

## <a name="related-classes"></a>Связанные классы

`CSplitterWnd` можно иметь несколько представлений в одном окне фрейма. `CPrintDialog` и `CPrintInfo` поддерживает возможность печати и предварительного просмотра представлений. `CRichEditDoc` и `CRichEditCntrItem` используются с `CRichEditView` для реализации возможностей контейнера OLE.

[CSplitterWnd](../mfc/reference/csplitterwnd-class.md)<br/>
Окно, в котором пользователь может разбить на несколько областей. Эти области могут быть регулируемого размера, указанного пользователя или фиксированного размера.

[CPrintDialog](../mfc/reference/cprintdialog-class.md)<br/>
Предоставляет стандартное диалоговое окно для печати файла.

[CPrintInfo](../mfc/reference/cprintinfo-structure.md)<br/>
Структура, содержащая сведения о задании печати или предварительного просмотра. Используемые `CView`для печати архитектуры.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Хранит список клиентских элементов управления OLE, которые находятся в `CRichEditView`.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
Предоставляет клиентский доступ к объект OLE, элементов, хранящихся в `CRichEditView`.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)
