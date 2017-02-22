---
title: "GetProjectPath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProjectPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProjectPath - метод"
ms.assetid: a5e51fe4-c068-47b7-9f2f-1a1d6c71a963
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetProjectPath
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Возвращает путь к каталогу проекта.  
  
## Синтаксис  
  
```  
  
      function GetProjectPath(   
   oProj    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
## Возвращаемое значение  
 Путь к каталогу проекта.  
  
## Заметки  
 Эта функция вызывается для получения пути к проекту.  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [GetProjectFile](../Topic/GetProjectFile.md)