---
title: Стили древовидного элемента управления
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
ms.openlocfilehash: 59cbed32d9be8fac84284b621bd4d1e17d5d92cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50453473"
---
# <a name="tree-control-styles"></a>Стили древовидного элемента управления

Дерево элемента управления ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) стили определяют внешний вид элемента управления дерева. Установить начальное стили при создании дерева. Можно извлекать и изменять стили после создания дерево с помощью [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) и [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) функции Windows, указав **GWL_STYLE** для *nIndex* параметра. Полный список стилей, см. в разделе [стили древовидного представления элемента управления окна](/windows/desktop/Controls/tree-view-control-window-styles) в пакете Windows SDK.

**TVS_HASLINES** стиля улучшает графическое представление иерархии дерева элемента управления путем рисования линии, которые связывают дочерних элементов до соответствующего родительского элемента. Этот стиль не содержит ссылок элементов в корне иерархии. Чтобы сделать это, вы должны будете объединить **TVS_HASLINES** и **TVS_LINESATROOT** стили.

Пользователя можно развернуть или свернуть список дочерних элементов родительского элемента, дважды щелкнув родительского элемента. Дерево, которое имеет **TVS_SINGLEEXPAND** вызывает стиля элемента выбранного для развертывания и для элемента не выбран, чтобы свернуть. Если мыши позволяет одним щелчком выбранный элемент и этот элемент имеет состояние закрытый, он будет расширен. Если выбранный элемент выбран от одного, при открытом, будет свернуто.

Дерево, которое имеет **TVS_HASBUTTONS** стиль добавляет кнопку слева от каждого родительского элемента. Пользователя можно щелкнуть кнопку, чтобы развернуть или свернуть дочерние элементы в качестве альтернативы дважды щелкать родительского элемента. **TVS_HASBUTTONS** не добавляет кнопки к элементам в корне иерархии. Чтобы сделать это, необходимо объединить **TVS_HASLINES**, **TVS_LINESATROOT**, и **TVS_HASBUTTONS**.

**TVS_EDITLABELS** стиль позволяет пользователю изменять метки элементов управления дерева. Дополнительные сведения об изменении меток см. в разделе [редактирование метки элемента управления дерева](../mfc/tree-control-label-editing.md) далее в этом разделе.

**TVS_NOTOOLTIPS** стиль отключает функцию автоматического средства совет элементы управления древовидного представления. Эта функция автоматически отображается всплывающая подсказка, содержащая заголовок элемента под курсором мыши, если заголовка не может быть видимой в данный момент.

## <a name="see-also"></a>См. также

[Использование CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

