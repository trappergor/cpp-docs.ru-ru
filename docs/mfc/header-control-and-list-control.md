---
title: Элементы управления "Заголовок" и "Список"
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 934b54de3266138225087d5519af2be51972cf9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240079"
---
# <a name="header-control-and-list-control"></a>Элементы управления "Заголовок" и "Список"

В большинстве случаев будет использоваться элемент управления заголовка, который внедряется в [CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView](../mfc/reference/clistview-class.md) объекта. Однако бывают случаи, где объект отдельный заголовок элемента управления является предпочтительным, таких как обработка данных, расположенных в столбцах или строках, в [CView](../mfc/reference/cview-class.md)-объект, производный от. В таких случаях требуется больший контроль над внешний вид и поведение по умолчанию элемента управления внедренных заголовка.

В общем случае возникает необходимость управления заголовка для предоставления стандартное поведение по умолчанию, вы можете использовать [CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView](../mfc/reference/clistview-class.md) вместо этого. Используйте `CListCtrl` при необходимости функциональные возможности элемента управления заголовка по умолчанию, внедренных в общем элементе управления представления списка. Используйте [CListView](../mfc/reference/clistview-class.md) при необходимости функциональные возможности элемента управления заголовка по умолчанию, внедренных в объект представления.

> [!NOTE]
>  Эти элементы управления включать встроенные заголовка элемента управления, только если управления представления списком создается с помощью **LVS_REPORT** стиля.

В большинстве случаев можно изменить внешний вид embedded заголовка элемента управления, изменив стили содержащегося элемента управления представления списка. Кроме того можно получить сведения об элементе управления заголовка с помощью функции-члены родительского элемента управления представления списка. Тем не менее полный контроль и доступа, атрибуты и стили в элементе управления внедренные заголовком, рекомендуется получить указатель на объект заголовка элемента управления.

Объект управления embedded заголовка может быть организован либо `CListCtrl` или `CListView` с помощью вызова соответствующего класса `GetHeaderCtrl` функция-член. Следующий код демонстрирует это:

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Использование списков изображений с элементами управления заголовка](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>См. также

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
