---
title: "novtable | Microsoft Docs"
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
  - "novtable"
  - "novtable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], novtable"
  - "novtable __declspec - ключевое слово"
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# novtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 Представляет собой расширенный атрибут `__declspec`.  
  
 Эта форма ключевого слова `__declspec` применима к любым объявлениям классов, но ее следует применять только к чистым классам интерфейсов, т. е к классам, для которых никогда не будут создаваться собственные экземпляры.  `__declspec` не позволяет компилятору создавать код для инициализации vfptr в конструкторах и деструкторе класса.  Во многих случаях это приводит к удалению единственной ссылки на связанную с классом таблицу vtable, в результате чего компоновщик удаляет ее.  Использование такой формы `__declspec` может приводить к значительному сокращению размера кода.  
  
 Если попытаться создать экземпляр класса, помеченного атрибутом `novtable`, а затем обратиться к члену класса, возникает нарушение прав доступа \(AV\).  
  
## Пример  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
  **In Y**   
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)