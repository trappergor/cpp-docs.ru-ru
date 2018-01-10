---
title: "_mm_insert_si64 _mm_inserti_si64 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
dev_langs: C++
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f7a2b52c8a41a3689cc668846e038505425aab4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64
**Блок, относящийся только к системам Microsoft**  
  
 Приводит к возникновению ошибки `insertq` инструкции для вставки bits из второго операнда в свой первый операнд.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Source1`  
 128-битовое поле с входных данных в его нижней 64 бита, в которые будет вставлено.  
  
 [in]`Source2`  
 128-битовое поле, с данными для вставки в низкая разряды.  Для `_mm_insert_si64`, также содержит дескриптор поля в его битов высокого уровня.  
  
 [in]`Length`  
 Целочисленная константа, указывающее длину этого поля для вставки.  
  
 [in]`Index`  
 Целочисленная константа, указывающее индекс младший значащий бит поля, в которую будут вставляться данные.  
  
## <a name="return-value"></a>Возвращаемое значение  
 128-битовое поле, которого младшие 64 бита содержат исходные младшие 64 разряда `Source1` с указанным битовое поле заменяется низкий биты `Source2`. Верхние 64 бит возвращаемое значение не определено.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция приводит к возникновению ошибки `insertq` инструкция insert биты в `Source2` в `Source1`. Существуют две версии, встроенные: `_mm_inserti_si64`, немедленно версией, и `_mm_insert_si64` тот не сразу.  Каждая версия извлекает битовое поле заданной длины из Source2 и вставляет его в Source1.  Извлеченные биты являются менее важные биты Source2.  Источник1 поле, в которую будет вставлена эти биты определяется длина и индекса его младший значащий бит.  Значение длины и индекса, получается mod 64, интерпретируются таким образом как 63 -1 до 127. Если сумма (низкой) индекс и длину поля (сокращенный) превышает 64, результаты не определены. Нулевое значение для длины полей интерпретируется как 64.  Если индекс поля длины и разрядное обоих равно нулю, что биты из `Source2` вставляются в `Source1`.  Если длина поля равна нулю, но индекс бит не равно нулю, результаты не определены.  
  
 В вызове _mm_insert_si64 длина поля содержатся в 77:72 bits Source2 и индекса в bits 69:64.  
  
 При вызове метода `_mm_inserti_si64` с аргументами, что компилятор не может определить для целочисленных констант, компилятор создает код для упаковки эти значения в регистре XMM и вызова `_mm_insert_si64`.  
  
 Чтобы определить аппаратную поддержку `insertq` вызов инструкции `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. При выполнении кода, использующего встроенную на оборудовании, которое не поддерживает `insertq` инструкции, результаты будут непредсказуемыми.  
  
## <a name="example"></a>Пример  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
```Output  
result1 = 0xfffffffff3210fff  
result2 = 0xfffffffff3210fff  
result3 = 0xfffffffff3210fff  
```  
  
**Завершение блока, относящегося только к системам Майкрософт**  
 Авторские права, 2007 дополнительных устройств Micro, Inc. Все права защищены. Воспроизвести с разрешения Дополнительно Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [_mm_extract_si64 _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)