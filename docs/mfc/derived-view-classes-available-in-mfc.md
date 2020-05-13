---
title: Производные классы представлений, доступные в MFC
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 12b31074e4fcc2ed6a83e3669e1044f5b9caedab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373506"
---
# <a name="derived-view-classes-available-in-mfc"></a>Производные классы представлений, доступные в MFC

В следующей таблице показаны классы представлений МФЦ и их отношения друг с другом. Возможности класса представления зависят от класса представления MFC, из которого он вытекает.

### <a name="view-classes"></a>Просмотр классов

|Class|Описание|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|Базовый класс всех представлений.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Базовый `CTreeView`класс `CListView` `CEditView`, `CRichEditView`, , и . Эти классы позволяют использовать архитектуру документов/просмотров с указанными общими элементами управления Windows.|
|[CEditView](../mfc/reference/ceditview-class.md)|Простое представление, основанное на управлении окном для отсвагиваем окни Windows. Позволяет вводить и редактировать текст и может быть использован в качестве основы для простого приложения редактор ассмеприра. Ознакомьтесь с командой `CRichEditView`.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Представление, содержащее объект [CRichEditCtrl.](../mfc/reference/cricheditctrl-class.md) Этот класс `CEditView`аналогин, `CEditView`но `CRichEditView` в отличие от, обрабатывает отформатированный текст.|
|[CListView](../mfc/reference/clistview-class.md)|Представление, содержащее объект [CListCtrl.](../mfc/reference/clistctrl-class.md)|
|[CTreeView](../mfc/reference/ctreeview-class.md)|Представление, содержащее объект [CTreeCtrl,](../mfc/reference/ctreectrl-class.md) для представлений, напоминающих окно Solution Explorer в Visual C.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|Базовый `CFormView`класс `CRecordView`, `CDaoRecordView`, и . Реализует прокрутку содержимого представления.|
|[CFormView](../mfc/reference/cformview-class.md)|Представление формы, представление, содержащее элементы управления. Приложение на основе форм предоставляет один или несколько таких интерфейсов формы.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Представление веб-браузера, с помощью которого пользователь приложения может просматривать сайты во Всемирной паутине, а также папки в локальной файловой системе и в сети. Представление веб-браузера также может работать как контейнер active document.|
|[CRecordView](../mfc/reference/crecordview-class.md)|Представление формы, отображающие записи базы данных ODBC в элементах управления. Если вы выберете поддержку ODBC в проекте, базовый класс представления — `CRecordView`это . Представление соединено с `CRowset` объектом.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Представление формы, отображающие записи базы данных DAO в элементах управления. Если вы выберете поддержку DAO в проекте, базовый класс представления — это `CDaoRecordView`. Представление соединено с `CDaoRecordset` объектом.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Представление формы, отображаемые записями OLE DB в элементах управления. Если вы выберете поддержку OLE DB в `COleDBRecordView`проекте, базовый класс представления — это . Представление соединено с `CRowset` объектом.|

> [!NOTE]
> По состоянию на Версию `CEditView` MFC `CCtrlView`4.0, является производным от .

Чтобы использовать эти классы в приложении, извлекайте из них классы представления приложения. Для получения соответствующей информации [см.](../mfc/scrolling-and-scaling-views.md) Для получения дополнительной информации [Overview: Database Programming](../data/data-access-programming-mfc-atl.md)о классах баз данных см.

## <a name="see-also"></a>См. также раздел

[Использование представлений](../mfc/using-views.md)
