---
title: __mulh
ms.date: 11/04/2016
f1_keywords:
- __mulh
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
ms.openlocfilehash: 122d7ff28a01c0b95c16c6a0f4cd20e883744d2e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034161"
---
# <a name="mulh"></a>__mulh

**Блок, относящийся только к системам Microsoft**

Возвращает старшие 64 разряда произведения двух 64-разрядных целых чисел со знаком.

## <a name="syntax"></a>Синтаксис

```
__int64 __mulh(
   __int64 a,
   __int64 b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in] Первое число для перемножения.

*b*<br/>
[in] Второе число для перемножения.

## <a name="return-value"></a>Возвращаемое значение

Старшие 64 разряда 128-разрядного результата умножения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__mulh`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// mulh.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__mulh)

int main()
{
    __int64 a = 0x0fffffffffffffffI64;
    __int64 b = 0xf0000000I64;

    __int64 result = __mulh(a, b); // the high 64 bits
    __int64 result2 = a * b; // the low 64 bits

    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",
             a, b, result, result2);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)