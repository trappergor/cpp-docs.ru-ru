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
ms.openlocfilehash: 4efd1c23c7e4d6f7d8e6fa9fe046f8de11c825a6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626534"
---
# <a name="adding-controls-by-hand"></a>Добавление элементов управления вручную

Можно либо [Добавить элементы управления в диалоговое окно с помощью редактора диалоговых окон](using-the-dialog-editor-to-add-controls.md) , либо добавить их самостоятельно с помощью кода.

Чтобы самостоятельно создать объект элемента управления, вы, как правило, внедряете управляющий объект C++ в диалоговом окне C++ или в объект окна фрейма. Как и многие другие объекты в платформе, для элементов управления требуется создание двух этапов. Необходимо вызвать функцию **создания** элемента управления в процессе создания родительского диалогового окна или окна фрейма. Для диалоговых окон это обычно делается в [онинитдиалог](reference/cdialog-class.md#oninitdialog), а для окон фрейма — в [OnCreate](reference/cwnd-class.md#oncreate).

В следующем примере показано, как можно объявить `CEdit` объект в объявлении класса производного диалогового окна, а затем вызвать `Create` функцию-член в `OnInitDialog` . Так как `CEdit` объект объявлен как внедренный объект, он автоматически создается при создании объекта диалогового окна, но должен быть инициализирован с помощью собственной `Create` функции-члена.

[!code-cpp[NVC_MFCControlLadenDialog#1](codesnippet/cpp/adding-controls-by-hand_1.h)]

Следующая `OnInitDialog` функция настраивает прямоугольник, затем вызывает метод, `Create` чтобы создать элемент управления Windows Edit и присоединить его к неинициализированному `CEdit` объекту.

[!code-cpp[NVC_MFCControlLadenDialog#2](codesnippet/cpp/adding-controls-by-hand_2.cpp)]

После создания объекта Edit можно также установить фокус ввода на элемент управления, вызвав `SetFocus` функцию члена. Наконец, возвращается значение 0, `OnInitDialog` чтобы отобразить, что вы установили фокус. Если возвращается ненулевое значение, диспетчер диалоговых окон устанавливает фокус на первый элемент элемента управления в списке элементов диалогового окна. В большинстве случаев элементы управления будут добавляться в диалоговые окна с помощью редактора диалоговых окон.

## <a name="see-also"></a>См. также раздел

[Создание и использование элементов управления](making-and-using-controls.md)<br/>
[Элементы управления](controls-mfc.md)<br/>
[CDialog:: Онинитдиалог](reference/cdialog-class.md#oninitdialog)
