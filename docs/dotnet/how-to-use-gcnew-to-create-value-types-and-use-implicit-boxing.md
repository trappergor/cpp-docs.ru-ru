---
title: "Практическое руководство. Использование gcnew для создания типов значений, а также использование неявной упаковки-преобразования | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "упаковка-преобразование, неявные"
  - "gcnew - ключевое слово [C++], создание типов значений"
  - "типы значений, создание"
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Использование gcnew для создания типов значений, а также использование неявной упаковки-преобразования
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

С помощью [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) от типа значения создает упакованный тип значения, которые затем могут быть помещены в управляемом, мусор\- собранная куча.  
  
## Пример  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## См. также  
 [Упаковка\-преобразование](../windows/boxing-cpp-component-extensions.md)