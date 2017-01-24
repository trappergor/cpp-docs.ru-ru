---
title: "_mm_stream_sd | Microsoft Docs"
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
  - "_mm_stream_sd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция _mm_stream_sd"
  - "Инструкция movntsd"
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mm_stream_sd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Записывает 64 бита данных в расположение в памяти без polluting кэши.  
  
## Синтаксис  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### Параметры  
 \[out\]`Dest`  
 Указатель на место, где начальной записываются данные.  
  
 \[входящий\] `Source`  
 Битовое значение 128, содержащих `double`, записываемое в его битах снизу 64.  
  
## Возвращаемое значение  
 Отсутствует.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный создает инструкцию `movntsd`.  Чтобы определить аппаратную поддержку этой инструкции вызовите внутреннего элемента `__cpuid` с `InfoType=0x80000001` и контрольный двоичный разряд 6 `CPUInfo[2] (ECX)`.  Этот бит 1, если оборудование поддерживает эту инструкцию, и 0 \- в противном случае.  
  
 Если запустить код, который использует внутренние `_mm_stream_sd` на оборудовании, не поддерживает инструкцию `movntsd` результаты становятся непредсказуемыми.  
  
## Пример  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
  **d \[0\] \= \-1 d \[1\] \= 1**   
## ЭЛЕМЕНТ, относящийся Майкрософт  
 Авторские права 2007 предварительными микро\- Устройствами, Inc все права защищены.  Воспроизведено с разрешением от предварительных микро\- Устройств, Inc  
  
## См. также  
 [\_mm\_stream\_ss](../Topic/_mm_stream_ss.md)   
 [\_mm\_store\_sd](http://msdn.microsoft.com/ru-ru/8e672d0d-0a96-45b9-a783-392a2457de42)   
 [\_mm\_sfence](http://msdn.microsoft.com/ru-ru/b6c0d18e-3628-4318-826b-45f66782e870)   
 [Streaming SIMD Extensions that Support the Cache](http://msdn.microsoft.com/ru-ru/8f03493a-d5f5-4457-892e-0b6540494872)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)