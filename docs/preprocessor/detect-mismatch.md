---
title: "detect_mismatch | Microsoft Docs"
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
  - "vc-pragma.detect_mismatch"
  - "detect_mismatch_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "detect_mismatch - прагма"
  - "прагмы, detect_mismatch"
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# detect_mismatch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помещает запись в объект.  Компоновщик проверяет эти записи на предмет наличия потенциальных несоответствий.  
  
## Синтаксис  
  
```  
#pragma detect_mismatch( "name", "value"))  
```  
  
## Заметки  
 При компоновке проекта компоновщик создает ошибку `LNK2038`, если проект содержит 2 объекта с одинаковыми именами `name`, но разными значениями `value`.  Используйте эту директиву \#pragma для предотвращения компоновки несогласованных объектных файлов.  
  
 Имя и значение являются строковыми литералами и подчиняются правилам для строковых литералов в отношении escape\-символов и объединения.  В них учитывается регистр, и они не могут содержать запятую, знак равенства, кавычки или символ `null`.  
  
## Пример  
 В этом примере создаются два файла, имеющие разные номера версий для одной метки версии.  
  
```  
// pragma_directive_detect_mismatch_a.cpp  
#pragma detect_mismatch("myLib_version", "9")  
int main ()  
{  
   return 0;  
}  
  
// pragma_directive_detect_mismatch_b.cpp  
#pragma detect_mismatch("myLib_version", "1")  
```  
  
 При компиляции обоих этих файлов с помощью командной строки `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` возникает ошибка `LNK2038`.  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)