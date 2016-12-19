---
title: "__super | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__super_cpp"
  - "__super"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__super - ключевое слово [C++]"
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __super
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Позволяет явно указать, что для переопределяемой функции вызывается реализация из базового класса.  
  
## Синтаксис  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## Заметки  
 На этапе разрешения перегрузки учитываются все доступные методы базового класса, и вызывается функция, которая обеспечивает наилучшее совпадение.  
  
 Ключевое слово `__super` может использоваться только в теле функции\-члена.  
  
 Ключевое слово `__super` не может использоваться с объявлением using.  Дополнительные сведения см. в разделе [Объявление using](../cpp/using-declaration.md).  
  
 В связи с введением [атрибутов](../windows/cpp-attributes-reference.md), внедряющих код, код может содержать один или несколько базовых классов с неизвестными именами, но включающих в себя методы, которые требуется вызвать.  
  
## Пример  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)