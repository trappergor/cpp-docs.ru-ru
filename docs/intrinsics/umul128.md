---
title: _umul128
ms.date: 11/04/2016
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: f7b33767155c4781d131a008d6d42dcc4015d07b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330519"
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
|`_umul128`|ARM, x64|\<Intrin.h >|

## <a name="example"></a>Пример

```
// umul128.c
// processor: IPF, x64

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