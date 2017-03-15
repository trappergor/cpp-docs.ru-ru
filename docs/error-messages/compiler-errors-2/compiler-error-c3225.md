---
title: "Ошибка компилятора C3225 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3225"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3225"
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C3225
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

аргумент универсального типа для "аргумента" не может быть "типом", он должен иметь тип значения или тип дескриптора  
  
 Аргумент универсального типа имеет неверный тип.  
  
 Для получения дополнительной информации см. [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).  
  
## Пример  
 Нельзя создавать экземпляры универсального типа в собственном типе.  В следующем примере возникает ошибка C3225.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## Пример  
 В следующем примере создается компонент с помощью C\#.  Обратите внимание, что ограничение указывает, что экземпляры универсального типа могут создаваться только с типом значения.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## Пример  
 В данном примере потребляется компонент, написанный на языке C\#, и нарушается ограничение, что экземпляры MyList могут создаваться только с типом значения, отличным от <xref:System.Nullable>.  В следующем примере возникает ошибка C3225.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```