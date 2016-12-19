---
title: "Toolbar Button Properties | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "size, toolbar buttons"
  - "toolbar buttons (in Toolbar editor), setting properties"
  - "Toolbar editor, toolbar button properties"
  - "status bars, active toolbar button text"
  - "command IDs, toolbar buttons"
  - "width, toolbar buttons"
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Toolbar Button Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Кнопки панели инструментов имеют следующие свойства:  
  
|Свойство.|Описание|  
|---------------|--------------|  
|**Идентификатор**|Определяет идентификатор кнопки.  Наиболее распространенные имена **идентификаторов** представлены в раскрывающемся списке.|  
|**Ширина**|Задает ширину кнопки.  Рекомендуемое значение — 16 пикселей.|  
|**Высота**|Задает высоту кнопки.  Обратите внимание, что высота кнопки является общим параметром для всех кнопок панели инструментов.  Рекомендуемое значение — 15 пикселей.|  
|**Запрос**|Определяет текст сообщений, которое отображается в строке состояния.  Если добавить \\n и имя, то у кнопки панели инструментов появится всплывающая подсказка.  Дополнительные сведения см. в разделе [Создание всплывающих подсказок](../mfc/creating-a-tool-tip-for-a-toolbar-button.md).|  
  
 Свойства **Ширина** и **Высота** есть у всех кнопок.  Ширина растрового изображения, используемого для создания панели инструментов, не может превышать значение 2048.  Таким образом, если для кнопки задать ширину 512 пикселей, на панели уместится четыре кнопки, а если ширина кнопки будет 513 пикселей, на панели можно будет разместить только три кнопки.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Требования  
 MFC или ATL  
  
## См. также  
 [Changing the Properties of a Toolbar Button](../mfc/changing-the-properties-of-a-toolbar-button.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)