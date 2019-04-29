---
title: _bittestandreset, _bittestandreset64
ms.date: 11/04/2016
f1_keywords:
- _bittestandreset64_cpp
- _bittestandreset
- _bittestandreset_cpp
- _bittestandreset64
helpviewer_keywords:
- btr instruction
- _bittestandreset intrinsic
- _bittestandreset64 intrinsic
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
ms.openlocfilehash: 53a9921b856a3bc489d1d8e1cd78a4cfa7493320
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349151"
---
# <a name="bittestandreset-bittestandreset64"></a>_bittestandreset, _bittestandreset64

**Блок, относящийся только к системам Microsoft**

Создание инструкции, которая проверяет разряд `b` адреса `a`, возвращает текущее значение и сбрасывает разряд в 0.

## <a name="syntax"></a>Синтаксис

```
unsigned char _bittestandreset(
   long *a,
   long b
);
unsigned char _bittestandreset64(
   __int64 *a,
   __int64 b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in, out] Указатель памяти для проверки.

*b*<br/>
[in] Позиция разряда для тестирования.

## <a name="return-value"></a>Возвращаемое значение

Разряд на указанной позиции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_bittestandreset`|x86, ARM, x64|
|`_bittestandreset64`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// bittestandreset.cpp
// processor: x86, IPF, x64
#include <stdio.h>
#include <limits.h>
#include <intrin.h>

#pragma intrinsic(_bittestandreset)

// Check the sign bit and reset to 0 (taking the absolute value)
// Returns 0 if the number is positive or zero
// Returns 1 if the number is negative
unsigned char absolute_value(long* p)
{
   const int SIGN_BIT = 31;
   return _bittestandreset(p, SIGN_BIT);
}

int main()
{
    long i = -112;
    unsigned char result;

    // Check the sign bit and reset to 0 (taking the absolute value)

    result = absolute_value(&i);
    if (result == 1)
        printf_s("The number was negative.\n");
}
```

```Output
The number was negative.
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)