---
title: "Функция SetErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetErrorInfo - метод"
ms.assetid: 78bca763-3f90-4e04-b566-b4b7fe2431b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция SetErrorInfo
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается функциями [OnWizFinish](../Topic/OnWizFinish.md) и [CanUseFileName](../ide/canusefilename.md) для предоставления сведений о текущей ошибке.  
  
## Синтаксис  
  
```  
  
      function SetErrorInfo(   
   oErrorObj   
);  
```  
  
#### Параметры  
 *oErrorObj*  
 Объект ошибки.  
  
## Заметки  
 Вызывается функциями [OnWizFinish](../Topic/OnWizFinish.md) и [CanUseFileName](../ide/canusefilename.md) для предоставления сведений о текущей ошибке.  Дополнительные сведения см. в описании метода <xref:Microsoft.VisualStudio.VsWizard.VCWizCtlClass.SetErrorInfo%2A> в документации по модели мастера Visual C\+\+.  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)