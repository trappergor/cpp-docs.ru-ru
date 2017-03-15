---
title: "Практическое руководство. Объявление закрепляющих указателей и типов значений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "закрепление указателей"
  - "типы значений, объявление"
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Практическое руководство. Объявление закрепляющих указателей и типов значений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Типы значений могут упаковываться неявно.  Затем можно объявить закрепляющий указатель на сам объект типа значения и использовать **pin\_ptr** на упакованный тип значения.  
  
## Пример  
  
### Код  
  
```  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
### Output  
  
```  
8  
7  
7  
```  
  
## См. также  
 [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)