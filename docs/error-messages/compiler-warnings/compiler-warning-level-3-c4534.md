---
title: "Предупреждение компилятора (уровень 3) C4534 | Microsoft Docs"
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
  - "c4534"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4534"
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4534
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'constructor' не будет конструктором по умолчанию для класса 'class' из\-за аргумента по умолчанию  
  
 В неуправляемом классе может быть конструктор с параметрами, обладающими значениями по умолчанию, и компилятор будет использовать его как конструктор по умолчанию.  Класс, отмеченный ключевым словом `value`, не будет использовать конструктор со значениями по умолчанию в качестве конструктора по умолчанию.  
  
 Для получения дополнительной информации см. [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C4534:  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```