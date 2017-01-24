---
title: "Ошибка компилятора C2976 | Microsoft Docs"
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
  - "C2976"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2976"
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2976
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : слишком мало аргументов типа  
  
 В универсальных параметрах или в шаблоне отсутствует один или несколько фактических аргументов.  Проверьте универсальный шаблон или объявление шаблона, чтобы найти правильное число параметров.  
  
 Эта ошибка может быть обусловлена отсутствием аргументов шаблона в компонентах STL.  
  
 Следующий пример приводит к возникновению ошибки C2976:  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 Ошибка C2976 также может возникнуть при использовании универсальных параметров:  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```