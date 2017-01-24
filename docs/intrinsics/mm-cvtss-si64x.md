---
title: "_mm_cvtss_si64x | Microsoft Docs"
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
  - "_mm_cvtss_si64x"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция cvtss2si"
  - "Встроенная функция _mm_cvtss_si64x"
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_cvtss_si64x
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Формирует версию удлиненную [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] числа с плавающей запятой одиночной точности convert скалярного на 64 инструкций целого числа \(`cvtss2si`\).  
  
## Синтаксис  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### Параметры  
 \[входящий\] `value`  
 Структура `__m128`, содержащий пункт\-значения плавающей запятой.  
  
## Возвращаемое значение  
 64 \- Целое число, результат преобразования первого значения с плавающей запятой в целое число.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Первый элемент значения структуры преобразован к целому числу и возвращается.  Биты элемента управления округления в MXCSR используются для определения расширения функциональности округления.  По умолчанию режим округления кружком, округление до ближайшего числа, даже если десятичная часть 0,5.  Поскольку структура `__m128` представляет регистр XMM, этот встроенный принимает значение регистра XMM и записывает его в системной памяти.  
  
 Эта процедура доступна только в качестве внутреннего элемента.  
  
## Пример  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
  **101**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [\_\_m128d](../cpp/m128d.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)