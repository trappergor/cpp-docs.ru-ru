---
title: "Ошибка компилятора C2179 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2179"
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": аргумент атрибута не может использовать параметры типа  
  
 Параметр универсального типа разрешается во время выполнения.  Однако параметр атрибута должен разрешаться во время компиляции.  Поэтому нельзя использовать параметр универсального типа в качестве аргумента атрибута.  
  
## Пример  
 В следующем примере возникает ошибка C2179.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```