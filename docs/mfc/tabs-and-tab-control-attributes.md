---
title: Вкладки и атрибуты элемента управления "Вкладка"
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
ms.openlocfilehash: 982ec40e330e2a7dda5c125d83e54751cd14416d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511240"
---
# <a name="tabs-and-tab-control-attributes"></a>Вкладки и атрибуты элемента управления "Вкладка"

У вас есть значительный контроль над внешним видом и поведением вкладок, составляющих элемент управления "Вкладка" ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Каждая вкладка может иметь метку, значок, состояние элемента и связанное с приложением 32-разрядное значение. Для каждой вкладки можно отобразить значок, метку или и то, и другое.

Кроме того, каждый элемент вкладки может иметь три возможных состояния: нажатое, ненажатое или выделенное. Это состояние может быть задано только путем изменения существующего элемента вкладки. Чтобы изменить существующий элемент вкладки, извлеките его с помощью вызова метода [DataItem](../mfc/reference/ctabctrl-class.md#getitem), измените `TCITEM` структуру (в частности, элементы данных *двстате* и *двстатемаск* ), а затем верните измененную `TCITEM` структуру с помощью вызова [Сетитем](../mfc/reference/ctabctrl-class.md#setitem). Если необходимо очистить состояния элементов всех элементов вкладки в `CTabCtrl` объекте, выполните вызов [деселекталл](../mfc/reference/ctabctrl-class.md#deselectall). Эта функция сбрасывает состояние всех элементов вкладки или всех элементов, кроме выбранного в данный момент.

Следующий код очищает состояние всех элементов вкладки, а затем изменяет состояние третьего элемента:

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

Дополнительные сведения об атрибутах табуляции см. в разделе [вкладки и атрибуты табуляции](/windows/win32/Controls/tab-controls) в Windows SDK. Дополнительные сведения о добавлении вкладок в элемент управления "Вкладка" см. в подразделе [Добавление вкладок к элементу управления вкладки](../mfc/adding-tabs-to-a-tab-control.md) далее в этой статье.

## <a name="see-also"></a>См. также

[Использование CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
