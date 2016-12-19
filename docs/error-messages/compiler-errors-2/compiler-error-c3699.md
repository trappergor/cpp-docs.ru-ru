---
title: "Ошибка компилятора C3699 | Microsoft Docs"
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
  - "C3699"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3699"
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3699
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": невозможно использовать этот косвенный оператор для типа "тип"  
  
 Была предпринята попытка использовать косвенный оператор, не разрешенный для типа `type`.  
  
## Пример  
 В следующем примере показано возникновение ошибки C3699.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## Пример  
 Обычное свойство не может иметь ссылочный тип.  Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  В следующем примере показано возникновение ошибки C3699.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## Пример  
 Эквивалентом синтаксиса "указатель на указатель" является обработка для отслеживания ссылок.  В следующем примере показано возникновение ошибки C3699.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```