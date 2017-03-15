---
title: "SetMergeProxySymbol | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetMergeProxySymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetMergeProxySymbol - метод"
ms.assetid: d6a9db59-2d5b-4431-98bc-785675e0eafe
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SetMergeProxySymbol
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта функция вызывается мастером для добавления символа \_MERGE\_PROXYSTUB, если это необходимо.  
  
## Синтаксис  
  
```  
  
      function SetMergeProxySymbol(   
   oProj    
);  
```  
  
#### Параметры  
 `oProj`  
 Объект выбранного проекта  
  
## Заметки  
 Эта функция вызывается мастером для добавления символа \_MERGE\_PROXYSTUB, если это необходимо.  
  
## Пример  
  
```  
SetMergeProxySymbol (selproj);  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)