---
title: Сопоставление команды меню с сочетанием клавиш (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da9807e552590513116a7a09a58609b2b576efcc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379740"
---
# <a name="associating-a-menu-command-with-an-accelerator-key-c"></a>Сопоставление команды меню с сочетанием клавиш (C++)

В некоторых ситуациях может потребоваться, чтобы программную команду можно было вызывать с помощью команды меню и сочетания клавиш. Это делается с помощью **меню** редактор, чтобы назначить один и тот же идентификатор ресурса команде меню и записи в таблице сочетаний клавиш приложения. Затем необходимо изменить [Заголовок](../windows/menu-command-properties.md) команды меню, чтобы в нем отображалось название сочетания клавиш.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш

1. В редакторе **меню** выберите нужную команду меню.

2. В [окне свойств](/visualstudio/ide/reference/properties-window)добавьте название сочетания клавиш в свойство **Заголовок** .

   - Сразу после заголовка меню введите escape-последовательность для табуляции (\t), чтобы все сочетания клавиш в меню были выровнены по левому краю.

   - Введите имя клавиши-модификатора (**Ctrl**, **Alt**, или **Shift**) следуют знак плюс (**+**) и имя, букву, или символ дополнительной клавиши.

       Например, чтобы назначить **Ctrl**+**O** для **откройте** команды **файл** меню изменить команды меню  **Заголовок** таким образом, чтобы он выглядел следующим образом:

        ```
        &Open...\tCtrl+O
        ```

       Команды меню в **меню** редактор будет обновлена с учетом нового названия, при вводе.

3. [Создайте запись в таблице сочетаний клавиш](../windows/adding-an-entry-to-an-accelerator-table.md) с помощью редактора **сочетаний клавиш** и назначьте ему тот же идентификатор ресурса, что и команде меню. Рекомендуется выбирать сочетания, которые легче запомнить.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Добавление команд в меню](../windows/adding-commands-to-a-menu.md)<br/>
[Редактор меню](../windows/menu-editor.md)