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
ms.openlocfilehash: 53dd6f1a7878d82a7f7ac48dd7082d791323941b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370470"
---
# <a name="header-control-and-list-control"></a>Элементы управления "Заголовок" и "Список"

В большинстве случаев вы будете использовать элемент управления заголовком, встроенный в объект [CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView.](../mfc/reference/clistview-class.md) Однако бывают случаи, когда желательно использовать отдельный объект управления заголовком, например, манипулирование данными, расположенными в столбцах или строках, в объекте, полученном [cView.](../mfc/reference/cview-class.md) В этих случаях требуется больший контроль над внешним видом и поведением встроенного заголовка по умолчанию.

В обычном случае, когда требуется, чтобы элемент управления заголовком обеспечивал стандартное поведение по умолчанию, вы можете использовать [вместо CListCtrl](../mfc/reference/clistctrl-class.md) или [CListView.](../mfc/reference/clistview-class.md) Используйте, `CListCtrl` когда требуется функциональность элемента управления заголовком по умолчанию, встроенная в общий элемент представления списка. Используйте [CListView,](../mfc/reference/clistview-class.md) когда требуется функциональность элемента управления заголовком по умолчанию, встроенного в объект представления.

> [!NOTE]
> Эти элементы управления включают встроенный элемент управления заголовком только в том случае, если элемент управления представления списка создан с помощью **LVS_REPORT** стиля.

В большинстве случаев внешний вид элемента управления встроенной заголовком может быть изменен путем изменения стилей управления представлениями, содержащего список. Кроме того, информация о контроле заголовка может быть получена через функции члена управления представления родительского списка. Однако для полного управления и доступа к атрибутам и стилям элемента управления встроенной заголовки рекомендуется получить указатель объекта управления заголовком.

К включенной объекту управления заголовком `CListCtrl` `CListView` можно получить доступ либо с `GetHeaderCtrl` одним из них, либо с вызовом к функции члена соответствующего класса. Следующий код демонстрирует это:

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать больше о

- [Использование списков изображений с элементами управления заголовком](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>См. также раздел

[Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
