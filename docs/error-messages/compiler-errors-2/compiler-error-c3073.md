---
title: "Ошибка компилятора C3073 | Microsoft Docs"
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
  - "C3073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3073"
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

тип: в классе ref нет определенного пользователем конструктора копии  
  
 В компиляции [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md) компилятор не будет генерировать копию конструктора для ссылочного типа.  В любой компиляции **\/clr** следует определить вашу собственную копию конструктора для ссылочного типа, если ожидается, что экземпляр типа должен быть скопирован.  
  
 Для получения дополнительной информации см. [Семантика стека C\+\+ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3073:  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```