---
title: "OffsetToLineNumber | Microsoft Docs"
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
  - "OffsetToLineNumber"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OffsetToLineNumber - функция"
ms.assetid: ac7e3c22-6b3b-432c-85cc-b50bbef9ce8c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OffsetToLineNumber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывается функцией [InsertIntoFunction](../ide/insertintofunction.md) для преобразования индекса в теле функции в номер строки.  
  
## Синтаксис  
  
```  
  
      function OffsetToLineNumber(   
   strString,   
   nPos    
);  
```  
  
#### Параметры  
 `strString`  
 Строка, содержащая тело функции.  Тело функции — это многострочный строковый литерал, в котором строки отделены парами символов "cr\-lf" \(возврат каретки и перевод строки\).  
  
 `nPos`  
 Положение внутри строкового литерала.  
  
## Возвращаемое значение  
 Строка в теле функции, в которой находится `nPos`.  Первая строка функции получает номер 1 \(не 0\).  
  
## Заметки  
 Находит номер строки для данной позиции в теле функции.  
  
 Эта функция вызывается функцией `InsertIntoFunction` для преобразования индекса, расположенного в параметре `nPos` в теле функции, в номер строки.  
  
## Пример  
  
```  
strString = "function DelFile(fso,  
 strWizTempFile)\r\n{\r\n\ttry\r\n\t{\r\nif   
(fso.FileExists(strWizTempFile))\r\nreturn true;\r\n";  
  
nLine =  OffsetToLineNumber(strString, 60);  
  
// The return value for the above is 5, because character 60 in the string   
// occurs in the 5th line within the string.  
```  
  
## См. также  
 [Настройка мастеров С\+\+ с помощью общих функций JScript.](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Функции JScript для мастеров C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [LineBeginsWith](../ide/linebeginswith.md)