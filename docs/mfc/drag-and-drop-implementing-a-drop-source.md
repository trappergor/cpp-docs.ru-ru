---
title: 'Путем перетаскивания: Реализация источника сброса'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
ms.openlocfilehash: cceed8517c7b63588c7b1b90e3306d90f0921b78
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300756"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Путем перетаскивания: Реализация источника сброса

В этой статье объясняется, как приложение предоставлять данные для операции перетаскивания и вставки.

Базовая реализация источника сброса является относительно простым. Первым шагом является определение, какие события начать операцию перетаскивания. Рекомендуется использовать рекомендации по пользовательскому интерфейсу определить начало операции перетаскивания, как выбор данных и **WM_LBUTTONDOWN** событий, происходящих в точке внутри выбранных данных. В примерах MFC OLE [OCLIENT](../visual-cpp-samples.md) и [HIERSVR](../visual-cpp-samples.md) следуйте приведенным ниже рекомендациям.

Если приложение является контейнером и выбранных данных имеет связанный или внедренный объект типа `COleClientItem`, вызовите его `DoDragDrop` функция-член. В противном случае создать `COleDataSource` объекта, инициализируйте его с элементом, выбранным и вызов объекта источника данных `DoDragDrop` функция-член. Если приложение является сервером, используйте `COleServerItem::DoDragDrop`. Сведения о настройке стандартное поведение перетаскивания и вставки, см. в статье [путем перетаскивания: Настройка](../mfc/drag-and-drop-customizing.md).

Если `DoDragDrop` возвращает **DROPEFFECT_MOVE**, немедленно удалить исходные данные из исходного документа. Не возвращает значение из `DoDragDrop` вступил в силу в источнике перетаскивания.

Дополнительные сведения:

- [Реализация конечного расположения сброса](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [Настройка операции перетаскивания](../mfc/drag-and-drop-customizing.md)

- [Создание и уничтожение объектов данных OLE и источников данных](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Управление объектами OLE данных и источников данных](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>См. также

[Перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)<br/>
[COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)<br/>
[CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)
