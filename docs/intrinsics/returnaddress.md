---
title: "_ReturnAddress | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция _ReturnAddress"
  - "Встроенная функция ReturnAddress"
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Только для систем Microsoft  
 Встроенный `_ReturnAddress` предоставляет адрес инструкции в вызывающей функции, которая будет выполнена после того как элемент управления будет возвращено вызывающему объекту.  
  
 Постройте следующие программы и через его в отладчике.  При заходе с помощью программы обратите внимание, адрес, который возвращается из `_ReturnAddress`.  Затем сразу после возврата из функции, `_ReturnAddress` использовалось, откройте [Практическое руководство. Использование окна дизассемблирования](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md) и обратите внимание, что адресом следующей инструкции при выполнении быть совпадения адрес, возвращенные из `_ReturnAddress`.  
  
 Оптимизация как встраивание могут повлиять на обратный адрес.  Например, если образец программы ниже компилироваться с [\/Ob1](../build/reference/ob-inline-function-expansion.md), то `inline_func` будет встроенным в вызывающем функцию, `main`.  Поэтому вызовы `_ReturnAddress` из `inline_func` и `main` будут каждую продукцию одно и то же значение.  
  
 При `_ReturnAddress` будет использоваться в программе компилированной с [\/clr](../build/reference/clr-common-language-runtime-compilation.md) функция, содержащего вызов `_ReturnAddress` будет компилированна как собственная функция.  При вызове компилированные функцией, такие как управляемые в функцию, содержащий `_ReturnAddress`, `_ReturnAddress` не могут вести себя так, как ожидалось.  
  
## Требования  
 **Файл заголовка** \<intrin.h\>  
  
## Пример  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [\_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)