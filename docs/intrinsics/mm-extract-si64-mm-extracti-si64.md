---
title: "_mm_extract_si64 _mm_extracti_si64 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
dev_langs:
- C++
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc65289ce52be9acb1cfe01d1149480a8381e3b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `extrq` инструкции, чтобы извлечь указанные биты из младшие 64 разряда своего первого аргумента.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 [in] `Source`  
 128-битовое поле, входных данных в его нижней 64 бита.  
  
 [in]  `Descriptor`  
 128-битовое поле, описывающее битовое поле для извлечения.  
  
 [in]  `Length`  
 Целое число, указывающее длину этого поля для извлечения.  
  
 [in]  `Index`  
 Целое число, указывающее индекс поля для извлечения  
  
## <a name="return-value"></a>Возвращаемое значение  
 128-битовое поле, с полем, извлеченные в его младших разрядов.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция приводит к возникновению ошибки `extrq` инструкции для извлечения биты в `Source`. Существуют две версии, встроенные: `_mm_extracti_si64` немедленно версией, и `_mm_extract_si64` тот не сразу.  Каждая версия извлекает из `Source` битовое поле, определяется его длина и индекса его младший значащий бит. Значение длины и индекса, получается mod 64, интерпретируются таким образом как 63 -1 до 127. Если сумма (сокращенный) индекс и длину поля (сокращенный) превышает 64, результаты не определены. Нулевое значение для длины полей интерпретируется как 64. Если индекс поля длины и разрядное обоих равно нулю, что биты из `Source` будут извлечены. Если длина поля равна нулю, но индекс бит не равно нулю, результаты не определены.  
  
 При обращении к _mm_extract_si64 `Descriptor` содержит индекс в битах 13:8 и длины поля данных, извлекаемых в бит 5:0...  
  
 При вызове метода `_mm_extracti_si64` с аргументами, что компилятор не может определить для целочисленных констант компилятор создает код для упаковки эти значения в реестр XMM (`Descriptor`) и для вызова `_mm_extract_si64`.  
  
 Чтобы определить аппаратную поддержку `extrq` инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. При выполнении кода, использующего это встроенная функция оборудование, не поддерживающий `extrq` инструкции, результаты будут непредсказуемыми.  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
result1 = 0x30eca86  
result2 = 0x30eca86  
result3 = 0x30eca86  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)