---
title: "CreateSafeName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateSafeName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSafeName - метод"
ms.assetid: 3a0dd4af-776d-4c25-aff9-4c539f173cb8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreateSafeName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает понятное имя C\+\+.  
  
## Синтаксис  
  
```  
  
      function CreateSafeName(   
   strName    
);  
```  
  
#### Параметры  
 `strName`  
 Прежнее имя.  
  
## Возвращаемое значение  
 Новое безопасное имя.  
  
## Заметки  
 Данная функция вызывается для создания понятного имя C\+\+ из имени, содержащего не используемые C\+\+ символы.  Допустимое имя C\+\+ может содержать прописные и строчные буквы, цифры или символ подчеркивания \("\_"\).  
  
 Данная функция проверяет прежнее имя знак за знаком, пропуская неиспользуемые символы.  Если прежнее имя не содержит понятных символов, тогда функция вернет новое имя "My".  Если новое понятное имя начинается с цифры, тогда функция вставит в начале нового имени "My".  
  
## Пример  
  
```  
// Get the project name  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Set the project name to the safe project name.   
var strSafeProjectName = CreateSafeName(strProjectName);  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)