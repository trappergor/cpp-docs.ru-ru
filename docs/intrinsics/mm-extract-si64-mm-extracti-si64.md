---
title: _mm_extract_si64, _mm_extracti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: e77ca5589ed50a4199921603afec1d9888c6cca5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040216"
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64

**Блок, относящийся только к системам Microsoft**

Создает `extrq` инструкции для извлечения битов из младшие 64 разряда первого аргумента.

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

*Источник*<br/>
[in] 128-битовое поле с входными данными в его нижние 64 бита.

*Дескриптор*<br/>
[in] 128-битовое поле, которое описывает битовое поле для извлечения.

*Длина*<br/>
[in] Целое число, указывающее длину этого поля для извлечения.

*Index*<br/>
[in] Целое число, указывающее индекс поля для извлечения

## <a name="return-value"></a>Возвращаемое значение

128-битовое поле, с полем, извлеченные в его младших разрядов.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция создает `extrq` инструкции для извлечения биты из `Source`. Существуют две версии этого, функция: `_mm_extracti_si64` является непосредственный версией, и `_mm_extract_si64` та же не сразу.  Каждая версия извлекает из `Source` битовое поле, определяется его длина и индекс ее наименее значимым битом. Значения длины и индекс берутся mod 64, интерпретируются таким образом как 63 -1 до 127. Если сумма (сокращение) индекс и длину поля (сокращение) больше, чем 64, результаты будут неопределенными. Нулевое значение для длины полей, интерпретируется как 64. Если индекс поля длины и разрядных обоих равно нулю, что биты из `Source` извлекаются. Если длина поля равна нулю, но индекс бит имеет ненулевое значение, результаты будут неопределенными.

При вызове _mm_extract_si64 `Descriptor` содержит индекс в массиве битов 13:8 и длины поля данных для извлечения в битах 5:0..

При вызове метода `_mm_extracti_si64` с аргументами, что компилятор не может определить быть целочисленные константы компилятор создает код для упаковки этих значений в регистр XMM (`Descriptor`) и вызова `_mm_extract_si64`.

Чтобы определить аппаратная поддержка для `extrq` инструкция, вызов `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. Если вы запустите код, использующий этот встроенный оборудования, который не поддерживает `extrq` инструкции, результаты будут непредсказуемыми.

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

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)