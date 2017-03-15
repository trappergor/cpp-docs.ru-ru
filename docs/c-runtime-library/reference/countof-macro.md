---
title: "Макрос _countof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_countof"
  - "countof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_countof - функция"
  - "countof - функция"
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Макрос _countof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вычисляют количество элементов в статически выделенном массиве.  
  
## Синтаксис  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### Параметры  
 `array`  
 Имя массива.  
  
## Возвращаемое значение  
 Количество элементов в массиве, выраженное как `size_t`.  
  
## Заметки  
 Убедитесь, что `array` действительно массив, а не указатель.  В C функция `_countof` дает ошибочные результаты, если `array` является указателем.  В C\+\+ если параметр `_countof` является указателем, функция `array` не скомпилируется.  
  
## Требования  
  
|Макрос|Обязательный заголовок|  
|------------|----------------------------|  
|`_countof`|\<stdlib.h\>|  
  
## Пример  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
  **sizeof\(arr\) \= 40 bytes**  
**\_countof\(arr\) \= 20 elements**   
## См. также  
 [Оператор sizeof](../../cpp/sizeof-operator.md)