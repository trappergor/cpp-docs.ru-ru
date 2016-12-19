---
title: "Предупреждение компилятора (уровень 1) C4288 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4288"
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение: "var": переменная цикла, объявленная внутри цикла for, используется вне цикла; это противоречит объявлению во внешней области видимости  
  
 При компиляции с параметрами [\/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **\/Zc:forscope\-** объявленная в цикле **for** переменная была использована вне области видимости цикла [for](../../cpp/for-statement-cpp.md).  Расширение Microsoft до языка C\+\+ позволяет данной переменной оставаться в области, при этом ошибка C4288 служит напоминанием о том, что первое объявление переменной не используется.  
  
 Дополнительные сведения об указании расширений Microsoft в циклах **for** с параметром \/Ze см. в разделе [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
 Следующий пример приводит к возникновению ошибки C4288:  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```