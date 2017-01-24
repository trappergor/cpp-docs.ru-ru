---
title: "make_public | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.make_public"
  - "make_public_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "make_public - прагма"
  - "прагмы, make_public"
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# make_public
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что собственный тип должен иметь открытый доступ к сборке.  
  
## Синтаксис  
  
```  
#pragma make_public(type)  
```  
  
#### Параметры  
 `type` — это имя типа, которому требуется предоставить открытый доступ к сборке.  
  
## Заметки  
 `make_public` удобно использовать, когда собственный тип, на который нужно сослаться, получен из файла .h, который невозможно изменить.  Если требуется использовать собственный тип в сигнатуре открытой функции в типе с открытой видимостью сборки, собственный тип также должен иметь открытый доступ к сборке; в противном случае компилятор выдаст предупреждение.  
  
 Ключевое слово `make_public` должно быть определено в глобальной области, и оно действует только с момента его объявления и до конца файла исходного кода.  
  
 Собственный тип может быть неявно или явно закрытым; дополнительные сведения см. в разделе [Видимость типов](../Topic/Type%20Visibility.md).  
  
## Пример  
 В следующем примере представлено содержимое файла .h, который содержит определения для двух собственных структур.  
  
```  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## Пример  
 В следующем примере кода используется файл заголовка и указывается, что, если собственные структуры явно не отметить как открытые с помощью `make_public`, компилятор выдаст предупреждение при попытке использовать собственные структуры в сигнатуре открытой функции в открытом управляемом типе.  
  
```  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)