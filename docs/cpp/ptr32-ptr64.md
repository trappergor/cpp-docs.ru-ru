---
title: "__ptr32, __ptr64 | Microsoft Docs"
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
  - "__ptr32_cpp"
  - "__ptr64_cpp"
  - "__ptr32"
  - "__ptr64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ptr32 - ключевое слово [C++]"
  - "__ptr64 - ключевое слово [C++]"
  - "_ptr32 - ключевое слово [C++]"
  - "_ptr64 - ключевое слово [C++]"
  - "ptr32 - ключевое слово [C++]"
  - "ptr64 - ключевое слово [C++]"
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __ptr32, __ptr64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 `__ptr32` представляет собственный указатель в 32\-разрядной системе, а `__ptr64` представляет собственный указатель в 64\-разрядной системе.  
  
 В следующем примере показано, как объявить каждый из этих типов указателей.  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 В 32\-разрядной системе указатель, объявленный с помощью `__ptr64`, усекается до 32\-разрядного указателя.  В 64\-разрядной системе указатель, объявленный с помощью `__ptr32`, приводится к 64\-разрядному указателю.  
  
> [!NOTE]
>  Использовать `__ptr32` или `__ptr64` при компиляции с **\/clr:pure** невозможно.  В противном случае создается ошибка `Compiler Error C2472`.  
  
## Пример  
 В следующем примере показано, как объявить и выделить указатели с ключевыми словами `__ptr32` и `__ptr64`.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
  **32**  
**64**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Фундаментальные типы](../cpp/fundamental-types-cpp.md)