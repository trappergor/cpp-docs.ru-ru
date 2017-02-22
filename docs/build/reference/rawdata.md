---
title: "/RAWDATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rawdata"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RAWDATA - параметр программы dumpbin"
  - "необработанные данный"
  - "RAWDATA - параметр (программа dumpbin)"
  - "-RAWDATA - параметр (программа dumpbin)"
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /RAWDATA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## Заметки  
 Этот параметр отображает необработанное содержимое каждого раздела в файле.  Аргументы управляют форматом отображения, как показано ниже:  
  
|Аргумент|Результат|  
|--------------|---------------|  
|1|Это значение используется по умолчанию.  Содержимое отображается в шестнадцатеричных байтах, а также как знаки ASCII, если имеют печатное представление.|  
|2|Содержимое отображается как шестнадцатеричные 2\-байтовые значения.|  
|4|Содержимое отображается как шестнадцатеричные 4\-байтовые значения.|  
|8|Содержимое отображается как шестнадцатеричные 8\-байтовые значения.|  
|НЕТ|Необработанные данные отбрасываются.  Этот аргумент полезен для управления выводом \/ALL.|  
|*Числовой*|Отображенные строки устанавливаются по ширине в соответствии со значениями `number` для каждой строки.|  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)