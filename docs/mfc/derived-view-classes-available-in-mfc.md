---
title: Производные классы представлений, доступные в MFC | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f8d058891b361b3747caafd9c4bd279c7626856
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426919"
---
# <a name="derived-view-classes-available-in-mfc"></a>Производные классы представлений, доступные в MFC

Ниже приведены классы MFC представления и их связи друг с другом. Возможности представления класса зависит от класса представления MFC, от которого он происходит.

### <a name="view-classes"></a>Классы представления

|Класс|Описание|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|Базовый класс для всех представлений.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Базовый класс `CTreeView`, `CListView`, `CEditView`, и `CRichEditView`. Эти классы позволяют использовать архитектуры document/view с указанной Общие элементы управления Windows.|
|[CEditView](../mfc/reference/ceditview-class.md)|Поле поля ввода простое представление, в зависимости от Windows. Позволяет вводить и изменять текст и может использоваться в качестве основы для приложения простого текстового редактора. См. также раздел `CRichEditView`.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Значение типа, содержащее представление [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) объекта. Этот класс является аналогом `CEditView`, но в отличие от `CEditView`, `CRichEditView` дескрипторы форматированного текста.|
|[CListView](../mfc/reference/clistview-class.md)|Значение типа, содержащее представление [CListCtrl](../mfc/reference/clistctrl-class.md) объекта.|
|[CTreeView](../mfc/reference/ctreeview-class.md)|Значение типа, содержащее представление [CTreeCtrl](../mfc/reference/ctreectrl-class.md) объект, для представления, которые похожи на окне обозревателя решений в Visual C++.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|Базовый класс `CFormView`, `CRecordView`, и `CDaoRecordView`. Реализует прокрутки просмотреть содержимое.|
|[Класс CFormView](../mfc/reference/cformview-class.md)|Представление формы, представление, содержащее элементы управления. Приложения на основе форм предоставляет один или несколько таких интерфейсов формы.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Представление веб-браузера, с помощью которого пользователь приложения может просматривать сайты в Интернете, а также папки в локальной файловой системе и в сети. Представление веб-браузера, также может работать как контейнер активного документа.|
|[CRecordView](../mfc/reference/crecordview-class.md)|Представление формы, в которой отображаются записи базы данных ODBC в элементах управления. Если выбрана поддержка ODBC в проекте, базовый класс представления является `CRecordView`. Представление подключен к `CRowset` объекта.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Представление формы, в которой отображаются записи базы данных DAO в элементах управления. Если выбрана поддержка DAO в проекте, базовый класс представления является `CDaoRecordView`. Представление подключен к `CDaoRecordset` объекта.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|Представление формы, в которой отображаются записи OLE DB в элементах управления. При выборе поддержки OLE DB в проекте, базовый класс представления — это `COleDBRecordView`. Представление подключен к `CRowset` объекта.|

> [!NOTE]
>  Начиная с версии 4.0, MFC `CEditView` является производным от `CCtrlView`.

Для использования этих классов в приложении, производных классов представления приложения от них. Дополнительные сведения см. в разделе [прокрутка и масштабирование представления](../mfc/scrolling-and-scaling-views.md). Дополнительные сведения о классы баз данных, см. в разделе [Обзор: программирования баз данных,](../data/data-access-programming-mfc-atl.md).

## <a name="see-also"></a>См. также

[Использование представлений](../mfc/using-views.md)

