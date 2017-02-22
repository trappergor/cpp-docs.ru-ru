---
title: "setlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "setlocale_CPP"
  - "vc-pragma.setlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "прагмы, setlocale"
  - "setlocale - прагма"
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# setlocale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет языковой стандарт \(страна или регион и язык\), используемый при преобразовании констант и строковых литералов с расширенными символами.  
  
## Синтаксис  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## Заметки  
 Поскольку алгоритм преобразования многобайтовых символов в расширенные символы может зависеть от языкового стандарта или компиляция может выполняться в среде с языковым стандартом, отличным от стандарта среды, в которой будет запускаться исполняемый файл, данная директива \#pragma позволяет указать целевой языковой стандарт во время компиляции.  Это гарантирует, что строки с расширенными символами будут сохраняться в правильном формате.  
  
 По умолчанию *строка\-языкового\-стандарта* имеет значение "".  
  
 Языковой стандарт "C" сопоставляет каждый символ в строке его значению с типом `wchar_t` \(unsigned short\).  Другие значения, допустимые в директиве `setlocale`, указаны в списке [Строки названий языков](../c-runtime-library/language-strings.md).  Например, можно указать директиву:  
  
```  
#pragma setlocale("dutch")  
```  
  
 Возможность указания строки с названием языка зависит от кодовых страниц и идентификаторов языков, поддерживаемых компьютером.  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)