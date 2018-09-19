---
title: _mm_insert_si64 _mm_inserti_si64 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
dev_langs:
- C++
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1c6b21ded6814492557ced792772508add06e53
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712851"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64

**Блок, относящийся только к системам Microsoft**  
  
Создает `insertq` инструкции для вставки биты из второго операнда в свой первый операнд.  
  
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
*Источник1*<br/>
[in] 128-разрядное поле с входными данными в его нижние 64 бита, в которые вставляются поле.  
  
*Source2*<br/>
[in] 128-разрядное поле с данными для вставки в его младшие разряда.  Для `_mm_insert_si64`, также содержит дескриптор поля в его старшие разряда.  
  
*Длина*<br/>
[in] Целочисленная константа, указывающее длину этого поля для вставки.  
  
*Index*<br/>
[in] Целочисленная константа, указывающее индекс поля, в который будут вставлены данные — наименее значащий бит.  
  
## <a name="return-value"></a>Возвращаемое значение  
 128-битовое поле, которого нижние 64 бита содержат исходное младшие 64 разряда `Source1` с полем указанный одноразрядный заменен младшие разряда `Source2`. Старшие 64 разрядов возвращаемого значения не определены.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта встроенная функция создает `insertq` инструкции для вставки биты из `Source2` в `Source1`. Существует две версии этого, функция: `_mm_inserti_si64`, является версией немедленно, и `_mm_insert_si64` та же не сразу.  Каждая версия извлекает битовое поле заданной длины из Source2 и вставляет его в Source1.  Извлеченные биты имеют младших разрядов Source2.  Источник1 поле, в которую будет вставлена эти биты определяется длина и индекс ее наименее значимым битом.  Значения длины и индекс берутся mod 64, интерпретируются таким образом как 63 -1 до 127. Если сумма индекса (низкой) и длину поля (сокращение) больше, чем 64, результаты будут неопределенными. Нулевое значение для длины полей, интерпретируется как 64.  Если индекс поля длины и разрядных обоих равно нулю, что биты из `Source2` вставляются `Source1`.  Если длина поля равна нулю, но индекс бит имеет ненулевое значение, результаты будут неопределенными.  
  
 При вызове _mm_insert_si64 длина поля содержатся в 77:72 bits Source2 и индекс в массиве битов 69:64.  
  
 При вызове метода `_mm_inserti_si64` с аргументами, что компилятор не может определить быть целочисленных констант, компилятор создает код для пакета эти значения в регистр XMM и вызова `_mm_insert_si64`.  
  
 Чтобы определить аппаратная поддержка для `insertq` вызов инструкции `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `insertq` инструкции, результаты будут непредсказуемыми.  
  
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

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.  
  
## <a name="see-also"></a>См. также  
 [_mm_extract_si64 _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)