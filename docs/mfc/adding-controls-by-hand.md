---
title: Добавление элементов управления вручную
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: c70539b49fcf2aa87f0bee375a87b38277b6ed42
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394810"
---
# <a name="adding-controls-by-hand"></a>Добавление элементов управления вручную

Вы можете либо [Добавление элементов управления в диалоговое окно редактора](../mfc/using-the-dialog-editor-to-add-controls.md) или добавить их вручную, с помощью кода.

Самостоятельно создать объект элемента управления, обычно будет внедрить управляющим объектом C++ в C++ диалогового окна или окна фрейма объекта. Как и многие другие объекты в структуре элементы управления требуют двух этапов построения. Необходимо вызвать элемент управления **создать** функция-член в процессе создания родительского диалоговое окно или фрейм окна. Для диалоговых окон, обычно это делается [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)и для окна фрейма в [OnCreate](../mfc/reference/cwnd-class.md#oncreate).

В следующем примере показано, как можно объявить `CEdit` объекта в объявлении класса диалоговое окно производного класса, а затем вызвать `Create` функции-члена в `OnInitDialog`. Так как `CEdit` объект объявляется как внедренный объект, автоматически создается при создании объекта диалоговое окно, но по-прежнему должны инициализироваться с собственным `Create` функция-член.

[!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]

Следующие `OnInitDialog` функция настраивает прямоугольник, затем вызывает `Create` для создания элемента управления редактирования Windows и присоединить ее к неинициализированным `CEdit` объекта.

[!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]

После создания объекта редактирования, можно также установить фокус ввода в элемент управления путем вызова `SetFocus` функция-член. Наконец, возвращается 0 из `OnInitDialog` Показать, что установка фокуса. Если возвращается ненулевое значение, диалоговое окно диспетчера устанавливает фокус на первый элемент управления в списке элементов диалогового окна. В большинстве случаев необходимо добавление элементов управления в диалоговые окна с помощью редактора диалоговых окон.

## <a name="see-also"></a>См. также

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)<br/>
[CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)
