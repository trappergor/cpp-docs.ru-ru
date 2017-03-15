---
title: "Функция IncludeCodeElementDeclaration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IncludeCodeElementDeclaration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncludeCodeElementDeclaration - метод"
ms.assetid: 714e76e4-76bc-439a-982a-cf9d4ada7677
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Функция IncludeCodeElementDeclaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Добавляет оператор include в файл `strInFile`, включая заголовок, где реализуется элемент кода `strCodeElemName`, если такой заголовок найден в проекте `oProj`.  
  
## Синтаксис  
  
```  
  
      function IncludeCodeElementDeclaration(   
   oProj,   
   strCodeElemName,   
   strInFile    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
 `strCodeElemName`  
 Полное имя элемента кода, поиск которого выполняется в заголовке определения.  
  
 `strInFile`  
 Файл, который будет включать заголовок определения, если последний будет найден.  
  
## Заметки  
 Добавляет оператор include в файл `strInFile`, включая заголовок, где реализуется элемент кода `strCodeElemName`, если такой заголовок найден в проекте `oProj`.  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)