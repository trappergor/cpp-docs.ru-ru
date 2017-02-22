---
title: "DoesIncludeExist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoesIncludeExist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoesIncludeExist - метод"
ms.assetid: 39751a3d-dfe5-423c-bd94-a53771c3e360
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DoesIncludeExist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Показывает, существует ли в файле оператор `#include` заданного заголовочного файла.  
  
## Синтаксис  
  
```  
  
      function DoesIncludeExist(   
   oProj,   
   strHeaderFile,   
   strInsertIntoFile    
);  
```  
  
#### Параметры  
 `oProj`  
 Выбранный проект.  
  
 *strHeaderFile*  
 Имя заголовочного файла для поиска.  
  
 `strInsertIntoFile`  
 Исходный файл, содержащий оператор `#include` заголовочного файла \(исключая путь\).  
  
## Возвращаемое значение  
 Значение **true**, если заданный заголовочный файл присутствует в файле; в противном случае — значение **false**.  
  
## Заметки  
 Показывает, существует ли оператор \#include указанного заголовочного файла в файле, заданном параметром `strInsertIntoFile`.  
  
## Пример  
  
```  
// Check to see if #include for atlbase.h   
// is included in the project's stdafx.h.  
// and add it if it is not.  
if (!DoesIncludeExist(selProj, "<atlbase.h>", strSTDAFX))  
   oCM.AddInclude("<atlbase.h>", strSTDAFX, vsCMAddPositionEnd);  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)