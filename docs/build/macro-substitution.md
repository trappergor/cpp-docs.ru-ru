---
title: "Макроподстановка | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "макросы, NMAKE - программа"
  - "программа NMAKE, макроподстановка"
  - "макроподстановка (NMAKE)"
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Макроподстановка
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При вызове *имя\_макроса* каждое появление строки *string1* в ее строке определения замещается строкой *string2*.  
  
## Синтаксис  
  
```  
$(macroname:string1=string2)  
```  
  
## Примечания  
 Макроподстановка выполняется с учетом регистра и буквально; *string1* и *string2* не могут вызывать макросы.  Подстановка не изменяет исходное определение.  Можно подставлять текст в любой предопределенный макрос, кроме [$$@](../build/filename-macros.md).  
  
 Не используйте пробелы и знаки табуляции перед двоеточием; все, что следует после двоеточия, интерпретируется как литерал.  Если строка *string2* пустая, все появления строки *string1* удаляются из строки определения макроса.  
  
## См. также  
 [Использование макроса NMAKE](../build/using-an-nmake-macro.md)