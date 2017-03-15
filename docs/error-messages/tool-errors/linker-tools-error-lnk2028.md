---
title: "Ошибка средств компоновщика LNK2028 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2028"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2028"
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка средств компоновщика LNK2028
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"exported\_function" \(decorated\_name\) в функции "function\_containing\_function\_call" \(decorated\_name\)  
  
 При попытке импортирования внутренней функции в чистый образ следует помнить о том, что явный вызов соглашений отличается во внутренней и чистой компиляции.  
  
## Пример  
 В примере этого кода создается компонент с экспортированной и внутренней функцией, явно вызывающий соглашение [\_\_cdecl](../Topic/__cdecl.md).  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## Пример  
 В следующем примере создается чистый клиент, использующий внутреннюю функцию.  Однако вызов соглашения в **\/clr:pure** представляет из себя [\_\_clrcall](../../cpp/clrcall.md).  Следующий пример приводит к возникновению ошибки LNK2028.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```