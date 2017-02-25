---
title: "_BitScanForward, _BitScanForward64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_BitScanForward"
  - "_BitScanForward_cpp"
  - "_BitScanForward64_cpp"
  - "_BitScanForward64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanForward intrinsic"
  - "BitScanForward intrinsic"
  - "bsf instruction"
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _BitScanForward, _BitScanForward64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Поиск данных маски от наименьшего значащего разряда \(LSB\) к наибольшему значащему разряду \(MSB\) для значащего разряда \(1\).  
  
## Синтаксис  
  
```  
unsigned char _BitScanForward(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanForward64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Параметры  
 \[выходной\] `Index`  
 Загруженный с позиции разряда первый значащий разряд \(1\) найден.  
  
 \[in\] `Mask`  
 32\-разрядное или 64\-разрядное значение для поиска.  
  
## Возвращаемое значение  
 0, если маска равна нулю; ненулевое значение в противном случае.  
  
## Заметки  
 Если найден значащий разряд, положение разряда первого найденного значащего разряда возвращается в качестве первого параметра.  Если значащий разряд не найден, возвращается 0; в противном случае возвращается 1.  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_BitScanForward`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_BitScanForward64`|ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Пример  
  
```  
// BitScanForward.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanForward)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanForward(&index, mask);  
   if (isNonzero)  
   {  
      cout << "Mask: " << mask << " Index: " << index << endl;  
   }  
   else  
   {  
      cout << "No set bits found.  Mask is zero." << endl;  
   }  
}  
```  
  
## Ввод  
  
```  
12  
```  
  
## Пример результатов выполнения  
  
```  
Enter a positive integer as the mask:   
Mask: 12 Index: 2  
```  
  
### Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)