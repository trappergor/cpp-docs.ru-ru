---
title: "Сопоставление команды меню с сочетанием клавиш | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26a44a8d1c2ddd32a63f86e0cba932da2437bad2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш
В некоторых ситуациях может потребоваться, чтобы программную команду можно было вызывать с помощью команды меню и сочетания клавиш. Для этого необходимо с помощью редактора меню назначить один и тот же идентификатор ресурса команде меню и записи в таблице сочетаний клавиш приложения. Затем необходимо изменить [Заголовок](../windows/menu-command-properties.md) команды меню, чтобы в нем отображалось название сочетания клавиш.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Сопоставление команды меню с сочетанием клавиш  
  
1.  В редакторе **меню** выберите нужную команду меню.  
  
2.  В [окне свойств](/visualstudio/ide/reference/properties-window)добавьте название сочетания клавиш в свойство **Заголовок** .  
  
    -   Сразу после заголовка меню введите escape-последовательность для табуляции (\t), чтобы все сочетания клавиш в меню были выровнены по левому краю.  
  
    -   Введите имя клавиши-модификатора (**CTRL**, **ALT**или **SHIFT**), а затем знак плюса (**+**) и имя, букву или символ дополнительной клавиши.  
  
         Например, чтобы назначить клавиши **CTRL+O** команде **Открыть** в меню **Файл** , необходимо изменить **Заголовок** команды меню следующим образом:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Команда меню в редакторе меню обновляется по мере ввода нового названия.  
  
3.  [Создайте запись в таблице сочетаний клавиш](../windows/adding-an-entry-to-an-accelerator-table.md) с помощью редактора **сочетаний клавиш** и назначьте ему тот же идентификатор ресурса, что и команде меню. Рекомендуется выбирать сочетания, которые легче запомнить.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Добавление команд в меню](../windows/adding-commands-to-a-menu.md)   
 [Редактор меню](../windows/menu-editor.md)