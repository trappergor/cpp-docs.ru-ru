---
title: "Creating a Tool Tip for a Toolbar Button | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tool tips [C++], adding to toolbar buttons"
  - "\n in tool tip"
  - "toolbar buttons [C++], tool tips"
  - "buttons [C++], tool tips"
  - "Toolbar editor, creating tool tips"
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating a Tool Tip for a Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Создание всплывающей подсказки  
  
1.  Выберите кнопку панели инструментов.  
  
2.  В поле свойства **Приглашение** [окна "Свойства"](../Topic/Properties%20Window.md), добавьте описание кнопки для строки состояния, после сообщения, добавьте add \\n и имя всплывающей подсказки.  
  
 Типичным примером всплывающей подсказки является кнопка "Печать" редактора WordPad:  
  
 1.  Откройте редактор WordPad.  
  
 2.  Наведите указатель мыши на кнопку панели инструментов **Печать**.  
  
 3.  Обратите внимание, что теперь под указателем мыши всплывает слово "Печать".  
  
 4.  Взгляните на строку состояния \(в самом низу окна WordPad\) – обратите внимание, что она теперь содержит текст "Печать активного документа".  
  
 "Печать" в шаге 3 — это "Имя всплывающей подсказки", а "Печать активного документа" из шага 4 — это "описание кнопки для строки состояния".  
  
 Если нужно получить этот эффект с помощью редактора **панели инструментов**, следует установить свойство **Приглашение** равным **Печать активного документа\\nПечать**.  
  
> [!NOTE]
>  Текст приглашения можно изменить с помощью [окна "Свойства"](../Topic/Properties%20Window.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 MFC или ATL  
  
## См. также  
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)