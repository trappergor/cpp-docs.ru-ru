---
title: "Ошибка компилятора C3821 | Microsoft Docs"
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
  - "C3821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3821"
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": в неуправляемой функции нельзя использовать управляемые типы или функции  
  
 Функции, использующие [setjmp](../../c-runtime-library/reference/setjmp.md) или встроенный код на языке ассемблера, не могут содержать типы значения или управляемые классы.  Чтобы устранить эту ошибку, удалите функцию `setjmp` и встроенный код на языке ассемблера, либо удалите управляемые объекты.  
  
 Ошибка C3821 также может возникать при попытке использования автоматического хранения в функции с переменным количеством аргументов.  Дополнительные сведения см. в разделах [Списки аргументов переменных \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) и [Семантика стека C\+\+ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C3821.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C3821.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C3821.  
  
```  
// C3821c.cpp  
// compile with: /clr:oldSyntax  
// processor: /x86  
__gc  class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A *a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```