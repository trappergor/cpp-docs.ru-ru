---
title: "Associating Menu Commands with Status Bar Text in MFC Applications | Microsoft Docs"
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
  - "status bars, associating menu items"
  - "menus, status bar text"
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Associating Menu Commands with Status Bar Text in MFC Applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Приложение может отображать описательный текст для каждой команды меню, которую может выбрать пользователь. Для этого необходимо назначить строку текста для каждой команды меню, используя свойство **Prompt** \(Подсказка\) в окне "Свойства". Если в [таблице строк](../mfc/string-editor.md) имеется строка, идентификатор которой совпадает с идентификатором команды, приложение MFC автоматически отобразит этот строковый ресурс в строке состояния выполняющегося приложения в момент, когда пользователь наведет указатель мыши на пункт меню.  
  
### Чтобы связать команду меню со строкой текста в строке состояния, выполните следующие действия.  
  
1.  В редакторе **меню** выберите команду меню.  
  
2.  В [окне "Свойства"](../Topic/Properties%20Window.md) в поле **Prompt** \(Подсказка\) введите нужный текст для строки состояния.  
  
 Сведения о добавлении ресурсов в проекты управляемого кода см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md)*Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Требования**  
  
 MFC  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)   
 [Adding Commands to a Menu](../Topic/Adding%20Commands%20to%20a%20Menu.md)   
 [Menu Editor](../Topic/Menu%20Editor.md)