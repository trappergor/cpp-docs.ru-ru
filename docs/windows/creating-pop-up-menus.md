---
title: "Создание всплывающих меню | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- context menus, Menu Editor
- pop-up menus, creating
- menus, pop-up
- menus, creating
- shortcut menus, creating
- pop-up menus, displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 529e0b4a659a3ea0c879db2c3b2a3bd4a9a3d160
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-pop-up-menus"></a>Создание всплывающих меню
[Всплывающие меню](../mfc/menus-mfc.md) отображают часто используемые команды. Они могут быть контекстно-зависимыми, т. е. зависеть от положения указателя. Использование всплывающего меню в приложении требует создания самого меню и привязки его к коду приложения.  
  
 После создания ресурса меню нужно обеспечить, чтобы код приложения загружал этот ресурс, и, используя [метод TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) , открывал меню на экране. Если пользователь откажется от выполнения команд всплывающего меню, щелкнув за его пределами, или щелкнет команду, будет выполнен возврат из этой функции. Если пользователь выберет команду, будет отправлено сообщение этой команды в то окно, дескриптор которого был передан.  
  
### <a name="to-create-a-pop-up-menu"></a>Создание всплывающего меню  
  
1.  [Создайте меню](../windows/creating-a-menu.md) с пустым заголовком (не вводите **заголовок**).  
  
2.  [Добавьте команды в новое меню](../windows/adding-commands-to-a-menu.md). Переместите первую команду меню под строку пустого заголовка (появится временный заголовок "Введите здесь"). Введите **заголовок** и прочие сведения.  
  
     Повторите эту процедуру для остальных команд всплывающего меню.  
  
3.  Сохраните ресурс меню.  
  
    > [!TIP]
    >  Дополнительные сведения о просмотре всплывающих меню см. в статье [Просмотр меню в виде всплывающего меню](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  

  
 **Требования**  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Подключение к приложению всплывающего меню](../windows/connecting-a-pop-up-menu-to-your-application.md)   
 [Редактор меню](../windows/menu-editor.md)