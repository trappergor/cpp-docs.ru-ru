---
title: Создание всплывающих меню (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c66f7074269e99b35785299800665be48cebef9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415724"
---
# <a name="creating-pop-up-menus-c"></a>Создание всплывающих меню (C++)

[Всплывающие меню](../mfc/menus-mfc.md) отображают часто используемые команды. Они могут быть контекстно-зависимыми, т. е. зависеть от положения указателя. Использование всплывающего меню в приложении требует создания самого меню и привязки его к коду приложения.

После создания ресурса меню, код приложения должен загрузить ресурс и использовать [метод TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) чтобы вызвать меню на экране. Если пользователь откажется от выполнения команд всплывающего меню, щелкнув за его пределами, или щелкнет команду, будет выполнен возврат из этой функции. Если пользователь выберет команду, будет отправлено сообщение этой команды в то окно, дескриптор которого был передан.

### <a name="to-create-a-pop-up-menu"></a>Создание всплывающего меню

1. [Создайте меню](../windows/creating-a-menu.md) с пустым заголовком (не вводите **заголовок**).

2. [Добавьте команды в новое меню](../windows/adding-commands-to-a-menu.md). Переместите первую команду меню под строку пустого заголовка (появится временный заголовок `Type Here`). Введите **заголовок** и прочие сведения.

   Повторите эту процедуру для остальных команд всплывающего меню.

3. Сохраните ресурс меню.

   > [!TIP]
   > Дополнительные сведения о просмотре всплывающих меню см. в статье [Просмотр меню в виде всплывающего меню](../windows/viewing-a-menu-as-a-pop-up-menu.md).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Подключение к приложению всплывающего меню](../windows/connecting-a-pop-up-menu-to-your-application.md)<br/>
[Редактор меню](../windows/menu-editor.md)