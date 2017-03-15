---
title: "Предупреждение компилятора (уровни 1 и 4) C4112 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4112"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4112"
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Предупреждение компилятора (уровни 1 и 4) C4112
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В директиве \#line требуется целое число между 1 и номером  
  
 Директива [\#Line](../Topic/%23line%20Directive%20\(C-C++\).md) указывает целочисленный параметр, который не входит в допустимый диапазон.  
  
 Если указанный параметр имеет значение меньше 1, счетчик строк сбрасывается до 1. Если указанный параметр больше, чем *номер*, представляющий определенный компилятором предел, то счетчик строк не изменяется. Это предупреждение уровня 1 в режиме совместимости с ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) и предупреждение уровня 4 в расширениях Майкрософт \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
 Следующий пример приводит к возникновению ошибки C4112:  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```