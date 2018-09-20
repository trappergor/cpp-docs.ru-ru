---
title: __ll_rshift | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71e9d9ef844dc2f46b28129611b76214658327ee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374422"
---
# <a name="llrshift"></a>__ll_rshift

**Блок, относящийся только к системам Microsoft**

Смещает 64-разрядное значение, определяемое первый параметр справа число битов, указанное в качестве второго параметра.

## <a name="syntax"></a>Синтаксис

```
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>Параметры

*Маска*<br/>
[in] 64-разрядное целое значение для сдвига вправо.

*nBit*<br/>
[in] Количество битов для сдвига, берется по модулю 64 в x64 и остаток от деления 32 на x86.

## <a name="return-value"></a>Возвращаемое значение

Маска сдвинуты `nBit` bits.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Если второй параметр больше, чем 64 в x64 (32 на x86), это число берется по модулю 64 (32 на x86) для определения числа битов для сдвига. `ll` Префикс указывает, что эта операция выполняется в на `long long`, другой имя `__int64`, 64-разрядной на целочисленный тип со знаком.

## <a name="example"></a>Пример

```
// ll_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_rshift)

int main()
{
   __int64 Mask = - 0x100;
   int nBit = 4;
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
   Mask = __ll_rshift(Mask, nBit);
   cout << hex << Mask << endl;
   cout << " - " << (- Mask) << endl;
}
```

## <a name="output"></a>Вывод

```
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

**Примечание** Если `_ull_rshift` уже используется, MSB сдвигом вправо значения были бы нулю, поэтому нужного результата не было бы получить в случае отрицательное значение.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)