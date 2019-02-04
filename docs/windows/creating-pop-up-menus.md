---
title: Создание всплывающих меню (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- shortcut menus [C++], connecting to applications
- pop-up menus
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
ms.openlocfilehash: cf2e3578f49cb6b4af8797052273211f699a6b4f
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702834"
---
# <a name="creating-pop-up-menus-c"></a>Создание всплывающих меню (C++)

[Всплывающие меню](../mfc/menus-mfc.md) отображают часто используемые команды. Они могут быть контекстно-зависимыми, т. е. зависеть от положения указателя. Использование всплывающего меню в приложении требует создания самого меню и привязки его к коду приложения.

После создания ресурса меню, код приложения должен загрузить ресурс и использовать [метод TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) чтобы вызвать меню на экране. Когда пользователь закрывает всплывающего меню, выбрав за его пределами или выбрал команду, чтобы вызвать эту функцию. Если пользователь выберет команду, будет отправлено сообщение этой команды в то окно, дескриптор которого был передан.

## <a name="to-create-a-pop-up-menu"></a>Создание всплывающего меню

1. [Создайте меню](../windows/creating-a-menu.md) с пустым заголовком (не вводите **заголовок**).

1. [Добавьте команды в новое меню](../windows/adding-commands-to-a-menu.md). Переместите первую команду меню под строку пустого заголовка (появится временный заголовок `Type Here`). Введите **заголовок** и прочие сведения.

   Повторите эту процедуру для остальных команд всплывающего меню.

1. Сохраните ресурс меню.

## <a name="to-connect-a-pop-up-menu-to-your-application"></a>Подключение к приложению всплывающего меню

1. Добавление обработчика сообщений для WM_CONTEXTMENU (к примеру). Дополнительные сведения см. в разделе [сопоставление сообщений с функциями](../mfc/reference/mapping-messages-to-functions.md).

1. Добавьте в обработчик сообщений следующий код:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > [CPoint](../atl-mfc-shared/reference/cpoint-class.md) передается сообщение обработчика задается в экранных координатах.

   > [!NOTE]
   > Подключение всплывающего меню к приложению требуется MFC.

## <a name="to-view-a-menu-resource-as-a-pop-up-menu"></a>Отображение ресурса меню в виде всплывающего меню

Как правило, при работе **меню** редактора, ресурс меню отображается в виде строки меню. Однако у вас могут оказаться ресурсы, добавленные в строку меню приложения, во время работы программы.

Щелкните правой кнопкой мыши меню и выберите **отобразить как всплывающее** в контекстном меню.

   Этот параметр является только режим отображения. само и не будет изменять меню.

   > [!NOTE]
   > Чтобы вернуться в представление строки меню, щелкните **отобразить как всплывающее** снова (которая снимается флажок и возвращает представление строки меню).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор меню](../windows/menu-editor.md)
