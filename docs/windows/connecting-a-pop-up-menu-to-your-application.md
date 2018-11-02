---
title: Подключение всплывающего меню для приложения C++
ms.date: 11/04/2016
helpviewer_keywords:
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- menus [C++], pop-up
- shortcut menus [C++], connecting to applications
ms.assetid: 295cbf0e-6416-478e-bc3d-472fb98e0e52
ms.openlocfilehash: 8a0cb64caaa58b464b0d5abb52093350c5e3cfeb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556498"
---
# <a name="connecting-a-pop-up-menu-to-your-c-application"></a>Подключение всплывающего меню для приложения C++

### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Подключение к приложению всплывающего меню

1. Добавление обработчика сообщений для WM_CONTEXTMENU (к примеру). Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).

2. Добавьте в обработчик сообщений следующий код:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > [CPoint](../atl-mfc-shared/reference/cpoint-class.md) передается сообщение обработчика задается в экранных координатах.

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Создание всплывающих меню](../windows/creating-pop-up-menus.md)<br/>
[Редактор меню](../windows/menu-editor.md)