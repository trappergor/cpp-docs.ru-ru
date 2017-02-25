---
title: "_mm_extract_si64, _mm_extracti_si64 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_mm_extracti_si64"
  - "_mm_extract_si64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция extrq"
  - "Встроенная функция _mm_extracti_si64"
  - "Встроенная функция _mm_extract_si64"
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# _mm_extract_si64, _mm_extracti_si64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Создает инструкцию `extrq` извлечь определенные биты из битов низкого уровня 64 своего первого аргумента.  
  
## Синтаксис  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### Параметры  
 \[in\]`Source`  
 Поле 128 бит с входными данными в его более низких 64 битах.  
  
 \[входящий\] `Descriptor`  
 Поле 128 бит, описывающее битовое поле для извлечения.  
  
 \[входящий\] `Length`  
 Целое число, задающее длину поля для извлечения.  
  
 \[входящий\] `Index`  
 Целое число, указывающее индекс поля для извлечения  
  
## Возвращаемое значение  
 Поле 128 бит с полем, извлеченным в его наименьших значительно битах.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный создает инструкцию `extrq` извлечь из `Source` биты. 2 Версии данного внутреннего элемента: `_mm_extracti_si64` быстрая версия и `_mm_extract_si64` non\-немедленное одно.  Каждая версия извлекает из `Source` битовое поле длиной, указанной его и индексом его наименьшего значительно бит.  Принимают значения длины и индексов mod 64, тем самым и \-1 и 127 интерпретируются как 63.  Если сумма \(уменьшенного индекса \(\) и уменьшенной\) длины поля превышает 64, то результаты не определены.  Нулевое значение длины поля, интерпретируется как 64.  Если индекс длины поля и оба бита равно нулю, 63:0 бит `Source` извлекается.  Если длина поля равна нулю, но индекс бита отличен от нуля, результаты не определены.  
  
 Вызову \_mm\_extract\_si64, `Descriptor` содержит индекс в 13:8 бит и длина поля данных, извлекаемых в 5:0 бит.  
  
 Если вызывается, `_mm_extracti_si64` с аргументами, компилятор не может определить, чтобы быть константами целого числа компилятор создает код для упаковки этих значений в регистр XMM \(`Descriptor`\) и вызвать `_mm_extract_si64`.  
  
 Чтобы определить аппаратную поддержку для инструкции `extrq`, вызовите внутреннего элемента `__cpuid` с `InfoType=0x80000001` и контрольный двоичный разряд 6 `CPUInfo[2] (ECX)`.  Этот бит будет 1, если инструкция поддерживается, и 0 \- в противном случае.  Если запустить код, который использует это встроенное оборудование, которое не поддерживает инструкцию `extrq` результаты становятся непредсказуемыми.  
  
## Пример  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
  **result1 result2 \= 0x30eca86 \= 0x30eca86 result3 \= 0x30eca86**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
 Авторские права 2007 предварительными микро\- Устройствами, Inc все права защищены.  Воспроизведено с разрешением от предварительных микро\- Устройств, Inc  
  
## См. также  
 [\_mm\_insert\_si64, \_mm\_inserti\_si64](../Topic/_mm_insert_si64,%20_mm_inserti_si64.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)