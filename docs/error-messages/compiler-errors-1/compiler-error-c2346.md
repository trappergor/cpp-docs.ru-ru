---
title: "Ошибка компилятора C2346 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2346"
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C2346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" не может быть скомпилирована как управляемая: причина  
  
 Компилятору не удалось скомпилировать функцию на языке MSIL.  
  
 Дополнительные сведения см. в разделах [managed, unmanaged](../../preprocessor/managed-unmanaged.md) и [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### Исправление этой ошибки  
  
1.  Удалите из функции код, который не может быть скомпилирован на языке MSIL.  
  
2.  Либо не компилируйте модуль с параметром **\/clr**, либо пометьте функцию как неуправляемую с помощью директивы pragma unmanaged.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2346.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```