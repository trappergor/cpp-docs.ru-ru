---
title: "Changing the Properties of a String | Microsoft Docs"
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
helpviewer_keywords: 
  - "resource identifiers, string properties"
  - "string tables, changing strings"
  - "strings [C++], properties"
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Properties of a String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Изменение строки или ее идентификатора  
  
1.  Откройте таблицу строк, дважды щелкнув соответствующий значок в [представлении ресурсов](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Если в проекте нет RC\-файла, см. раздел [Создание нового файла скрипта ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Выберите редактируемую строку и дважды щелкните столбец **Идентификатор**, **Значение** или **Заголовок**.  Теперь разработчик может:  
  
    -   Выбрать **идентификатор** в **раскрывающемся списке идентификаторов** или прямо ввести нужный идентификатор.  
  
    -   Ввести другое число в столбце **Значение**.  
  
    -   Ввести изменения в столбец **Заголовок**.  
  
        > [!NOTE]
        >  Свойства строки можно также изменить в [окне "Свойства"](../Topic/Properties%20Window.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты \(предназначенные для выполнения в общеязыковой среде CLR\) см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделах [Пошаговое руководство. Локализация приложений Windows Forms](http://msdn.microsoft.com/ru-ru/9a96220d-a19b-4de0-9f48-01e5d82679e5) и [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [String Editor](../mfc/string-editor.md)   
 [Строки](_win32_Strings)   
 [О строках](_win32_About_Strings_cpp)