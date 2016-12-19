---
title: "Доступ к аргументам | Microsoft Docs"
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
  - "c.arguments"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "макрос доступа к аргументам [C++]"
  - "списки аргументов переменной длины"
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Доступ к аргументам
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Макросы `va_arg`, `va_end` и `va_start` предоставляют доступ к аргументам функции, когда число аргументов является переменным.  Эти макросы определены в STDARG.H для ANSI C совместимости и в VARARGS.H для обеспечения совместимости с UNIX System V.  
  
### Макросы доступа к аргументам  
  
|Макрос|Применение|Эквивалент в .NET Framework|  
|------------|----------------|---------------------------------|  
|[va\_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Извлекает аргумент из списка|[\<caps:sentence id\="tgt9" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Класс System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Сбрасывает указатель|[\<caps:sentence id\="tgt12" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Класс System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
|[va\_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|Устанавливает указатель на начало списка аргументов|[\<caps:sentence id\="tgt15" sentenceid\="f260effcc218d99ea9ab361455fd493c" class\="tgtSentence"\>Класс System::ParamArrayAttribute\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx)|  
  
## См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)