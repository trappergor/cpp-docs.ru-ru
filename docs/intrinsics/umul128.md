---
title: _umul128
ms.date: 11/04/2016
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: 94f26a6baeb4d3440d7f16af298b9880b91860f2
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220495"
---
# <a name="umul128"></a>_umul128

**Блок, относящийся только к системам Microsoft**

Умножает два 64-разрядных целых числа без знака, переданных в качестве первых двух аргументов, и помещает старшие 64 разряда произведения в 64-разрядное целое число без знака, на которое указывает `HighProduct` и возвращает младшие 64 разряда произведения.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 _umul128(
   unsigned __int64 Multiplier,
   unsigned __int64 Multiplicand,
   unsigned __int64 *HighProduct
);
```

#### <a name="parameters"></a>Параметры

*Множитель*<br/>
[in] Первый 64-разрядное целое для умножения.

*Множитель*<br/>
[in] Второй 64-разрядное целое для умножения.

*HighProduct*<br/>
[out] Старшие 64 разряда продукта.

## <a name="return-value"></a>Возвращаемое значение

Младшие 64 разряда произведения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_umul128`|X64|\<Intrin.h >|

## <a name="example"></a>Пример

```
// umul128.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_umul128)

int main()
{
    unsigned __int64 a = 0x0fffffffffffffffI64;
    unsigned __int64 b = 0xf0000000I64;
    unsigned __int64 c, d;

    d = _umul128(a, b, &c);

    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
