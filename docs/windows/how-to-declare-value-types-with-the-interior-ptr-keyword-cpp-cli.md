---
title: "Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ptr - ключевое слово"
  - "типы значений, объявление"
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`interior_ptr` можно использовать с типом значения.  
  
> [!IMPORTANT]
>  Эта функция языка поддерживается параметром компилятора **\/clr**, но не параметром компилятора **\/ZW**.  
  
## Пример  
  
### Описание  
 В следующем примере [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] показано, как использовать `interior_ptr` с типом значения.  
  
### Код  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### Output  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## Пример  
  
### Описание  
 В типе значения, указатель `this` равен interior\_ptr.  
  
 В теле нестатической функции\-члене типа значения `V` `this` является выражением типа `interior_ptr<V>`, значением которого является адрес объекта, для которого вызывается функция.  
  
### Код  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## Пример  
  
### Описание  
 В следующем примере показано, как использовать оператор address\-of со статическими членами.  
  
 Адрес статического члена типа Visual C\+\+ создает собственный указатель.  Адрес статического члена типа значения является управляемым указателем, так как член типа значения выделен в куче среды выполнения и может быть перемещен сборщиком мусора.  
  
### Код  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### Output  
  
```  
22  
23  
hello  
```  
  
## См. также  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)