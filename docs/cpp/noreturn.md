---
title: "noreturn | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noreturn_cpp"
  - "noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], noreturn"
  - "noreturn __declspec - ключевое слово"
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# noreturn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 Атрибут `__declspec` сообщает компилятору, что функция не возвращается.  Как следствие, компилятор знает, что код после вызова функции **\_\_declspec\(noreturn\)** недостижим.  
  
 Если компилятор обнаруживает функцию с путем элемента управления, которая не возвращает значение, он создает предупреждение \(C4715\) или сообщение об ошибке \(C2202\).  Если путь к элементу управления недостижим из\-за того, что функция никогда не возвращается, можно использовать **\_\_declspec\(noreturn\)**, чтобы избежать предупреждения или ошибки.  
  
> [!NOTE]
>  Добавление **\_\_declspec\(noreturn\)** в функцию, возврат которой ожидается, может привести к неопределенному поведению.  
  
## Пример  
 В следующем примере предложение **else** не содержит оператор return.  Объявление `fatal` как **\_\_declspec\(noreturn\)** позволяет избежать сообщения об ошибке или предупреждающего сообщения.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)