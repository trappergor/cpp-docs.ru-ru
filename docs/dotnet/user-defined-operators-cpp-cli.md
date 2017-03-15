---
title: "Пользовательские операторы (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "пользовательские операторы в /clr"
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пользовательские операторы (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяемые пользователем операторы для управляемых типов разрешены как статические члены или члены экземпляра, или в глобальной области.  Однако только статические операторы доступны через метаданные для клиентов, записываются на языке, отличном от Visual C\+\+.  
  
 В ссылочного типа, один из параметров статического определяемого пользователем оператора должно быть одним из следующих:  
  
-   Дескриптор \(^`type` \) на экземпляр того типа.  
  
-   Косвенное обращение ссылочного типа " \(" ^& " или type^%`type`\) дескриптора к экземпляру того типа.  
  
 В типе значения, один из параметров статического определяемого пользователем оператора должно быть одним из следующих:  
  
-   Того же типа, что и внешний тип значения.  
  
-   Косвенное обращение указатель \(^`type`\) в состав типу.  
  
-   Косвенное обращение ссылочного типа \(`type`% или `type`&\) для включающего его тип.  
  
-   Косвенное обращение ссылочного типа \(`type`^% или ^&`type`\) дескриптора.  
  
 Можно указать следующие операторы:  
  
|Оператор|Унарные\/бинарные формы?|  
|--------------|------------------------------|  
|\!|Унарный|  
|\!\=|Binary|  
|%|Binary|  
|&|Унарный и бинарный|  
|&&|Binary|  
|\*|Унарный и бинарный|  
|\+|Унарный и бинарный|  
|\+\+|Унарный|  
|,|Binary|  
|\-|Унарный и бинарный|  
|\-\-|Унарный|  
|\-\>|Унарный|  
|\/|Binary|  
|\<|Binary|  
|\<\<|Binary|  
|\<\=|Binary|  
|\=|Binary|  
|\=\=|Binary|  
|\>|Binary|  
|\>\=|Binary|  
|\>\>|Binary|  
|^|Binary|  
|false|Унарный|  
|true|Унарный|  
|&#124;|Binary|  
|&#124;&#124;|Binary|  
|~|Унарный|  
  
## Пример  
  
```  
// mcppv2_user-defined_operators.cpp  
// compile with: /clr  
using namespace System;  
public ref struct X {  
   X(int i) : m_i(i) {}  
   X() {}  
  
   int m_i;  
  
   // static, binary, user-defined operator  
   static X ^ operator + (X^ me, int i) {  
      return (gcnew X(me -> m_i + i));  
   }  
  
   // instance, binary, user-defined operator  
   X^ operator -( int i ) {  
      return gcnew X(this->m_i - i);  
   }  
  
   // instance, unary, user-defined pre-increment operator  
   X^ operator ++() {  
      return gcnew X(this->m_i++);  
   }  
  
   // instance, unary, user-defined post-increment operator  
   X^ operator ++(int i) {  
      return gcnew X(this->m_i++);  
   }  
  
   // static, unary user-defined pre- and post-increment operator  
   static X^ operator-- (X^ me) {  
      return (gcnew X(me -> m_i - 1));  
   }  
};  
  
int main() {  
   X ^hX = gcnew X(-5);  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX + 1;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX = hX - (-1);  
   System::Console::WriteLine(hX -> m_i);  
  
   ++hX;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX++;  
   System::Console::WriteLine(hX -> m_i);  
  
   hX--;  
   System::Console::WriteLine(hX -> m_i);  
  
   --hX;  
   System::Console::WriteLine(hX -> m_i);  
}  
```  
  
  **\-5**  
**\-4**  
**\-3**  
**\-2**  
**\-1**  
**\-2**  
**\-3**   
## Пример  
 В следующем примере показано синтез оператора, который доступен только при использовании **\/clr** компилироваться.  Синтез оператора создается форма назначения бинарного оператора, если не указать, где левое — от side оператора присваивания имеет тип среды CLR.  
  
```  
// mcppv2_user-defined_operators_2.cpp  
// compile with: /clr  
ref struct A {  
   A(int n) : m_n(n) {};  
   static A^ operator + (A^ r1, A^ r2) {  
      return gcnew A( r1->m_n + r2->m_n);  
   };  
   int m_n;  
};  
  
int main() {  
   A^ a1 = gcnew A(10);  
   A^ a2 = gcnew A(20);  
  
   a1 += a2;   // a1 = a1 + a2   += not defined in source  
   System::Console::WriteLine(a1->m_n);  
}  
```  
  
  **30**   
## См. также  
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)