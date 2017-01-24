---
title: "Спецификация ширины printf | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf - функция, поля описания формата"
  - "printf - функция, спецификация ширины"
ms.assetid: 8b4a1b1e-bf6e-414f-a1b6-a9b6f1b6ce92
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Спецификация ширины printf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В спецификации формата второе необязательное поле — это спецификация ширины.  Аргумент `width` — неотрицательное целое десятичное число, управляющее минимальным количеством выходных символов.  Если количество знаков в выходном значении ниже заданной ширины, к значению слева или справа будут добавлены пробелы, в зависимости от того, определен ли флаг выравнивания по левому краю \(`-`\), в количестве, необходимом, чтобы достичь минимальной ширины.  Если `width` имеет префикс 0, то начальные нули добавляются к целому числу или числу с плавающей запятой при преобразовании до тех пор, пока не будет достигнута минимальная ширина, кроме случаев преобразования в бесконечность или NAN.  
  
 Спецификация ширины никогда не вызывает отбрасывание значения.  Если количество знаков в выходном значении больше определенной ширина или если `width` не указан, то все символы значения считаются выходными в соответствии со спецификацией [точность](../c-runtime-library/precision-specification.md).  
  
 Если спецификация ширины — звездочка \(`*`\), аргумент `int` из списка аргументов предоставляет значение.  Аргумент `width` должен предшествовать форматируемому значению в списке аргументов как показано в следующем примере:  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 Отсутствующее или небольшое значение `width` в спецификации формата не приводит к усечению выходного значения.  Если результат преобразования превышает значение `width`, поле расширяется, чтобы вместить результат преобразования.  
  
## См. также  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Синтаксис описания формата: функции printf и wprintf](../Topic/Format%20Specification%20Syntax:%20printf%20and%20wprintf%20Functions.md)   
 [Директивы флагов](../Topic/Flag%20Directives.md)   
 [Спецификация точности](../c-runtime-library/precision-specification.md)   
 [Спецификация размера](../c-runtime-library/size-specification.md)   
 [Символы поля типа printf](../c-runtime-library/printf-type-field-characters.md)