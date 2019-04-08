---
title: __shiftleft128
ms.date: 11/04/2016
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: 5fcb797694c7a45dc4f2113f3d2ed4a2f578c894
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024859"
---
# <a name="shiftleft128"></a>__shiftleft128

**Блок, относящийся только к системам Microsoft**

Сдвигает 128-разрядную величину, представленную в виде двух величин по 64-разряда `LowPart` и `HighPart`, влево на количество разрядов, указанное в `Shift` и возвращает старшие 64 разряда результата.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __shiftleft128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

#### <a name="parameters"></a>Параметры

*Значение подверсии*<br/>
[in] Младшие 64 разряда 128-разрядной величины для сдвига.

*HighPart*<br/>
[in] Старшие 64 разряда 128-разрядной величины для сдвига.

*Сдвиг*<br/>
[in] Количество битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Старшие 64 разряда результата.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__shiftleft128`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Это значение `Shift` всегда берется по модулю 64, поэтому, например, при вызове метода`__shiftleft128(1, 0, 64)`, функция будет сдвигать влево  разряды `0` младшей части возвращать старшую часть `0`, а не `1`, как в противном случае можно было ожидать.

## <a name="example"></a>Пример

```
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__shiftright128](../intrinsics/shiftright128.md)<br/>
[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)