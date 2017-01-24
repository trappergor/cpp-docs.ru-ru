---
title: "Ошибка средств компоновщика LNK2020 | Microsoft Docs"
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
  - "LNK2020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2020"
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK2020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неразрешенная лексема "лексема"  
  
 Эта ошибка аналогична неопределенной внешней ошибки, за исключением того, что ссылка разрешается через метаданные.  В метаданных все функции и данные должны быть определены.  
  
 Чтобы устранить данную ошибку:  
  
-   следует определить пропущенную функцию или данные, либо  
  
-   включить объектный файл или библиотеку, в которой уже определены пропущенные данные или функция.  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки LNK2020.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## Пример  
 LNK2020 может также возникнуть в случае, когда создается переменная управляемого типа шаблона, но не создается экземпляр типа.  
  
 Следующий пример демонстрирует причины возникновения ошибки LNK2020.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```