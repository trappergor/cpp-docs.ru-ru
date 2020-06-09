---
title: Производные классы представлений, доступные в MFC
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: dc0f0b10ea291db32c576a7d36b7fc19728fa6ce
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616987"
---
# <a name="derived-view-classes-available-in-mfc"></a>Производные классы представлений, доступные в MFC

В следующей таблице показаны классы представления MFC и их связи друг с другом. Возможности класса представления зависят от класса представления MFC, от которого он наследуется.

### <a name="view-classes"></a>Классы представлений

|Класс|Описание|
|-----------|-----------------|
|[CView](reference/cview-class.md)|Базовый класс всех представлений.|
|[CCtrlView](reference/cctrlview-class.md)|Базовый класс для `CTreeView` , `CListView` , `CEditView` и `CRichEditView` . Эти классы позволяют использовать архитектуру документов и представлений с указанными стандартными элементами управления Windows.|
|[CEditView](reference/ceditview-class.md)|Простое представление, основанное на элементе управления "поле ввода Windows". Позволяет вводить и редактировать текст и может использоваться в качестве основания для простого текстового редактора. Ознакомьтесь с командой `CRichEditView`.|
|[CRichEditView](reference/cricheditview-class.md)|Представление, содержащее объект [CRichEditCtrl](reference/cricheditctrl-class.md) . Этот класс аналогичен `CEditView` , но, в отличие от `CEditView` , `CRichEditView` обрабатывает форматированный текст.|
|[CListView](reference/clistview-class.md)|Представление, содержащее объект [CListCtrl](reference/clistctrl-class.md) .|
|[CTreeView](reference/ctreeview-class.md)|Представление, содержащее объект [CTreeCtrl](reference/ctreectrl-class.md) , для представлений, которые похожи на обозреватель решенийое окно в Visual C++.|
|[CScrollView](reference/cscrollview-class.md)|Базовый класс для `CFormView` , `CRecordView` и `CDaoRecordView` . Реализует прокрутку содержимого представления.|
|[CFormView](reference/cformview-class.md)|Представление формы, содержащее элементы управления. Приложение на основе форм предоставляет один или несколько таких интерфейсов форм.|
|[CHtmlView](reference/chtmlview-class.md)|Представление веб-браузера, с помощью которого пользователь приложения может просматривать сайты в Интернете, а также папки в локальной файловой системе и в сети. Представление веб-браузера также может работать как активный контейнер документа.|
|[CRecordView](reference/crecordview-class.md)|Представление формы, которое отображает записи базы данных ODBC в элементах управления. Если в проекте выбрана поддержка ODBC, то базовым классом представления будет `CRecordView` . Представление подключено к `CRowset` объекту.|
|[CDaoRecordView](reference/cdaorecordview-class.md)|Представление формы, в котором отображаются записи базы данных DAO в элементах управления. Если в проекте выбрана поддержка DAO, то базовым классом представления будет `CDaoRecordView` . Представление подключено к `CDaoRecordset` объекту.|
|[COleDBRecordView](reference/coledbrecordview-class.md)|Представление формы, которое отображает записи OLE DB в элементах управления. Если в проекте выбрать OLE DB поддержки, то базовым классом представления будет `COleDBRecordView` . Представление подключено к `CRowset` объекту.|

> [!NOTE]
> Начиная с MFC версии 4,0, `CEditView` является производным от `CCtrlView` .

Чтобы использовать эти классы в приложении, следует создать из них классы представления приложения. Связанные сведения см. в разделе [представления прокрутки и масштабирования](scrolling-and-scaling-views.md). Дополнительные сведения о классах базы данных см. в разделе [Обзор: программирование базы данных](../data/data-access-programming-mfc-atl.md).

## <a name="see-also"></a>См. также раздел

[Использование представлений](using-views.md)
