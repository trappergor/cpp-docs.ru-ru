---
title: "Предоставление контекстной справки. | Microsoft Docs"
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
  - "контекстная справка"
  - "контекстная справка, Специальный мастер"
  - "пользовательские мастера, реализация Справки"
ms.assetid: c6c4d961-29d3-4d16-9f39-b12545aba540
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Предоставление контекстной справки.
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При использовании для создания мастера [специального мастера](../Topic/Application%20Settings,%20Custom%20Wizard.md) специальный мастер внедряет в мастер кнопку **Справка**.  
  
 Каждый HTM\-файл в проекте содержит следующий код для обеспечения поддержки кнопки **Справка** в мастере.  
  
```  
<BUTTON CLASS="BUTTONS" ID="HelpBtn" ACCESSKEY="H"  
 onClick="window.external.OnHelp('vc.appwiz.custom.overview');">  
```  
  
 Метод <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.OnHelp%2A> задает ключевое слово для файла справки HTML, связанного с этой страницей мастера.  Дополнительные сведения о создании HTML\-файлов справки, связанных со страницей, см. на [домашней странице справки HTML](vsconhh1start).  Для создания собственной справки для данной страницы мастера следует заменить строку `'vc.appwiz.custom.overview'` ключевым словом, которое идентифицирует раздел справки HTML для страницы.  
  
 **Примечание**.   Данный HTM\-файл не может быть интегрирован в скомпилированную справку MSDN.  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)