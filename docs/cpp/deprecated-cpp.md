---
title: "deprecated (C++) | Microsoft Docs"
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
  - "deprecated"
  - "deprecated_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], нерекомендуемый"
  - "__declspec - нерекомендованное ключевое слово"
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deprecated (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(Используется только в системах Microsoft\) За указанным ниже исключением объявление **deprecated** предлагает те же функциональные возможности, что и директива pragma [deprecated](../Topic/deprecated%20\(C-C++\).md).  
  
-   Объявление **deprecated** позволяет указать определенные формы перегрузок функций как нерекомендуемые, тогда как форма директивы pragma применяется ко всем перегруженным формам имени функции.  
  
-   Объявление **deprecated** позволяет указать сообщение, которое будет отображаться во время компиляции.  Текст сообщения может быть взят из макроса.  
  
-   Макросы могут отмечаться как нерекомендуемые только с помощью директивы pragma **deprecated**.  
  
 Если компилятор обнаруживает использование нерекомендуемого идентификатора, выдается предупреждение [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  
  
## Пример  
 В следующем примере показано, как отметить функции как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемая функция.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## Пример  
 В следующем примере показано, как отметить классы как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемый класс.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)