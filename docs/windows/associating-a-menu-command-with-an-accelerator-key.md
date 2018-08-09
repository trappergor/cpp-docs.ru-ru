---
title: Сопоставление команды меню с сочетанием клавиш | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e4b1665e54a03bf7d5f4705aaa3d76962ed16a0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649976"
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш
В некоторых ситуациях может потребоваться, чтобы программную команду можно было вызывать с помощью команды меню и сочетания клавиш. Это делается с помощью **меню** редактор, чтобы назначить один и тот же идентификатор ресурса команде меню и записи в таблице сочетаний клавиш приложения. Затем необходимо изменить [Заголовок](../windows/menu-command-properties.md) команды меню, чтобы в нем отображалось название сочетания клавиш.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш  
  
1.  В редакторе **меню** выберите нужную команду меню.  
  
2.  В [окне свойств](/visualstudio/ide/reference/properties-window)добавьте название сочетания клавиш в свойство **Заголовок** .  
  
    -   Сразу после заголовка меню введите escape-последовательность для табуляции (\t), чтобы все сочетания клавиш в меню были выровнены по левому краю.  
  
    -   Введите имя клавиши-модификатора (**Ctrl**, **Alt**, или **Shift**) следуют знак плюс (**+**) и имя, букву, или символ дополнительной клавиши.  
  
         Например, чтобы назначить **Ctrl**+**O** для **откройте** команды **файл** меню изменить команды меню  **Заголовок** таким образом, чтобы он выглядел следующим образом:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Команды меню в **меню** редактор будет обновлена с учетом нового названия, при вводе.  
  
3.  [Создайте запись в таблице сочетаний клавиш](../windows/adding-an-entry-to-an-accelerator-table.md) с помощью редактора **сочетаний клавиш** и назначьте ему тот же идентификатор ресурса, что и команде меню. Рекомендуется выбирать сочетания, которые легче запомнить.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Добавление команд в меню](../windows/adding-commands-to-a-menu.md)   
 [Редактор меню](../windows/menu-editor.md)