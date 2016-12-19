---
title: "Ошибка компилятора C2893 | Microsoft Docs"
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
  - "C2893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2893"
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ошибка при специализации шаблона функции 'имя шаблона  
  
 При попытке компилятора специализировать шаблон функции произошла ошибка.  Эта ошибка может быть вызвана многими причинами.  
  
 В общем, чтобы устранить ошибку C2893, необходимо просмотреть сигнатуру функции и убедиться, что есть возможность создать экземпляры всех типов.  
  
## Пример  
 C2893 возникает, так как параметр шаблона `f` `T` должен был быть `std::map<int,int>`, но в `std::map<int,int>` нет члена `data_type` \(нельзя создать экземпляр `T::data_type` с помощью `T = std::map<int,int>`\).  Следующий пример приводит к возникновению ошибки C2893.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```