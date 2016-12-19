---
title: "GetInterfaceType | Microsoft Docs"
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
  - "GetInterfaceType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInterfaceType - метод"
ms.assetid: cc6403a8-0c2b-47f7-a8f7-9db95df87d5a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetInterfaceType
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает тип интерфейса.  
  
## Синтаксис  
  
```  
  
      function GetInterfaceType(   
   oInterface    
);  
```  
  
#### Параметры  
 *oInterface*  
 Объект <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeInterface>.  
  
## Возвращаемое значение  
 Строка, указывающая тип интерфейса, например пользовательский, сдвоенный, диспетчерский или автоматизированный OLE.  
  
## Заметки  
 Данная функция вызывается, чтобы получить тип интерфейса.  
  
## Пример  
 См. раздел [GetMaxID](../ide/getmaxid.md).  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [Функция GetInterfaceClasses](../Topic/GetInterfaceClasses.md)