---
title: "Предупреждение компилятора (уровень 1) C4162 | Microsoft Docs"
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
  - "C4162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4162"
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier" : функция с компоновкой C не обнаружена  
  
 Функция с компоновкой С объявлена, но не обнаружена.  
  
 Чтобы разрешить это предупреждение, компилируйте в C\-файле \(вызовите компилятор С\).  Если необходимо вызвать компилятор C\+\+, поместите внешний "С" до объявления функции.  
  
 В следующем примере формируется предупреждение C4162:  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```