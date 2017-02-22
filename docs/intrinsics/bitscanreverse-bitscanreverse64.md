---
title: "_BitScanReverse, _BitScanReverse64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_BitScanReverse64"
  - "_BitScanReverse_cpp"
  - "_BitScanReverse"
  - "_BitScanReverse64_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_BitScanReverse intrinsic"
  - "BitScanReverse intrinsic"
  - "bsr instruction"
ms.assetid: 2520a207-af8b-4aad-9ae7-831abeadf376
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _BitScanReverse, _BitScanReverse64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Найти данные маски от наибольшего значащего разряда \(MSB\) к наименьшему значащему разряду \(LSB\) для значащего разряда \(1\).  
  
## Синтаксис  
  
```  
unsigned char _BitScanReverse(    unsigned long * Index,    unsigned long Mask ); unsigned char _BitScanReverse64(    unsigned long * Index,    unsigned __int64 Mask );  
```  
  
#### Параметры  
 \[выходной\] `Index`  
 Загруженный с позиции разряда первый значащий разряд \(1\) найден.  
  
 \[in\] `Mask`  
 32\-разрядное или 64\-разрядное значение для поиска.  
  
## Возвращаемое значение  
 Не нуль, если `Index` был установлен, или 0, если значащие разряды не найдены.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_BitScanReverse`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_BitScanReverse64`|ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]||  
  
## Пример  
  
```  
// BitScanReverse.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_BitScanReverse)  
  
int main()  
{  
   unsigned long mask = 0x1000;  
   unsigned long index;  
   unsigned char isNonzero;  
  
   cout << "Enter a positive integer as the mask: " << flush;  
   cin >> mask;  
   isNonzero = _BitScanReverse(&index, mask);  
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
Mask: 12 Index: 3  
```  
  
### Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)