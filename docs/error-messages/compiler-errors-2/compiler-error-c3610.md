---
title: "Ошибка компилятора C3610 | Microsoft Docs"
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
  - "C3610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3610"
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"типзначения": тип значения должен быть упакован перед вызовом метода "метод"  
  
 По умолчанию тип значения не находится в управляемой куче.  Прежде чем можно будет вызывать методы классов среды выполнения .NET, например методы класса `Object`, необходимо переместить тип значения в управляемую кучу.  
  
 Ошибка C3610 возникает только при использовании параметра **\/clr:oldSyntax**.  
  
 Следующий пример приводит к возникновению ошибки C3610:  
  
```  
// C3610.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class A {};  
  
int main() {  
   A a;  
   a.GetType(); // C3610  
  
   // OK  
   __box A* ovar = __box(a);  
   ovar->GetType();  
}  
```