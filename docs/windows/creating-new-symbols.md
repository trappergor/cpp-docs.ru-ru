---
title: "Creating New Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.creating"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "New Symbol dialog box"
  - "symbols, creating"
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Creating New Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В начале работы над новым проектом может оказаться удобным спланировать необходимые имена символов перед созданием ресурсов, которым они будут назначены.  
  
### Создание нового символа с помощью диалогового окна символов ресурсов  
  
1.  В [диалоговом окне "Символы ресурсов"](../windows/resource-symbols-dialog-box.md) выберите команду **Создать**.  
  
2.  В поле **Имя** введите имя символа.  
  
3.  Оставьте предложенное значение.  
  
     \-или\-  
  
     Введите в поле **Значение** новое значение.  
  
4.  Нажмите кнопку **ОК** для добавления нового символа в список символов.  
  
 Если будет введено имя символа, которое уже существует, появится сообщение о том, что символ с таким именем уже определен.  Нельзя определить два и несколько символов с одинаковыми именами, но можно определить разные символы с одинаковыми числовыми значениями.  Дополнительные сведения см. в статьях [Ограничения для имен символов](../windows/symbol-name-restrictions.md) и [Ограничения для значений символов](../Topic/Symbol%20Value%20Restrictions.md).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы приложений](../Topic/Resources%20in%20Desktop%20Apps.md) *Руководства разработчика .NET Framework*. Сведения о том, как вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Требования  
  
 Win32  
  
## См. также  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)