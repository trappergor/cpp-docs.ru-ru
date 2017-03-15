---
title: "unary_delegate (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::unary_delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_delegate - функция [STL/CLR]"
ms.assetid: b3ee253c-98e8-466e-a272-505e47aed061
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# unary_delegate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Genereic класс описывает от аргумента делегата.  Он используется определить делегат с точки зрения его аргументу и возвращаемых типов.  
  
## Синтаксис  
  
```  
generic<typename Arg,  
    typename Result>  
    delegate Result unary_delegate(Arg);  
```  
  
#### Параметры  
 Аргумент  
 Тип аргумента.  
  
 Результат  
 Возвращаемый тип.  
  
## Заметки  
 Genereic делегат описываются функции от аргумента.  
  
 Обратите внимание, что для:  
  
 `unary_delegare<int, int> Fun1;`  
  
 `unary_delegare<int, int> Fun2;`  
  
 типы `Fun1` и `Fun2` синонимы, а для:  
  
 `delegate int Fun1(int);`  
  
 `delegate int Fun2(int);`  
  
 они не одного типа.  
  
## Пример  
  
```  
// cliext_unary_delegate.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
int hash_val(wchar_t val)   
    {   
    return ((val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate<wchar_t, int> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
  **хэш \(L'а\) \= 5**  
**хэш \(L'б\) \= 22**   
## Требования  
 **Заголовок:**\<cliext\/functional\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [binary\_delegate](../Topic/binary_delegate%20\(STL-CLR\).md)   
 [binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary\_delegate\_noreturn](../dotnet/unary-delegate-noreturn-stl-clr.md)