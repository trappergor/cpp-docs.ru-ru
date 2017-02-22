---
title: "How to: Search for Symbols in Resources | Microsoft Docs"
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
  - "symbols, finding"
  - "resources [Visual Studio], searching for symbols"
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# How to: Search for Symbols in Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### Поиск символов в ресурсах  
  
1.  В меню **Правка** выберите команду **Найти символ**.  
  
2.  В [диалоговом окне "Поиск символа"](http://msdn.microsoft.com/ru-ru/63e93d9c-784f-418d-a76a-723da5ff5d96) в поле **Найти** выберите предыдущую строку поиска из раскрывающегося списка или введите сочетание клавиш, которое требуется найти \(например, ID\_ACCEL1\).  
  
    > [!TIP]
    >  Чтобы использовать [регулярные выражения](../Topic/Using%20Regular%20Expressions%20in%20Visual%20Studio.md) для поиска, нужно использовать [команду "Найти в файлах"](../Topic/Find%20Command.md) в меню **Правка** вместо команды **Поиск символа**.  Чтобы включить регулярные выражения, нужно установить флажок **Использовать регулярные выражения** в [диалоговом окне "Поиск"](http://msdn.microsoft.com/ru-ru/dad03582-4931-4893-83ba-84b37f5b1600).  Затем можно щелкнуть кнопку со стрелкой вправо, расположенную справа от поля **Найти**, чтобы отобразить список регулярных выражений, которые можно использовать в поисковом запросе.  При выборе выражения из этого списка оно подставляется как текст для поиска в поле **Найти**.  
  
3.  Выберите нужные параметры **поиска**.  
  
4.  Нажмите кнопку **Найти далее**.  
  
    > [!NOTE]
    >  Нельзя выполнять поиск символов в строках, сочетаниях клавиш и двоичных ресурсах.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 Win32  
  
## См. также  
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)