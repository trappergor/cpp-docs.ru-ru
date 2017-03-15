---
title: "Ошибка компилятора C2951 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2951"
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

объявления типов допускаются только в глобальной области видимости или же области видимости пространства имен или класса  
  
 Универсальные классы и шаблоны нельзя объявлять вне пределов глобальной области видимости или области видимости пространства имен.  Если универсальные классы и шаблоны объявляются во включаемом файле, то он должен находиться в глобальной области видимости.  
  
 Следующий пример приводит к возникновению ошибки C2951:  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 Ошибка C2951 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```