---
title: __ll_rshift
ms.date: 09/02/2019
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
ms.openlocfilehash: ad17991d84acb7e531baf9435610ebd566197a22
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217499"
---
# <a name="__ll_rshift"></a>__ll_rshift

**Блок, относящийся только к системам Microsoft**

Сдвигает 64-разрядное значение, заданное первым параметром вправо, на число битов, заданное вторым параметром.

## <a name="syntax"></a>Синтаксис

```C
__int64 __ll_rshift(
   __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Параметры

*Виде*\
окне 64-разрядное целочисленное значение, которое нужно сдвинуть вправо.

*нбит*\
окне Число битов для сдвига, остаток от деления 64 на x64 и остаток от деления 32 на x86.

## <a name="return-value"></a>Возвращаемое значение

Маска, смещенная по `nBit` битам.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__ll_rshift`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Если второй параметр больше 64 в x64 (32 на x86), то это число берется по модулю 64 (32 на x86), чтобы определить число битов для сдвига. Префикс указывает, что это операция над `long long`, еще одно имя для `__int64`, 64-разрядного целочисленного типа со знаком. `ll`

## <a name="example"></a>Пример

```cpp
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

```Output
ffffffffffffff00
- 100
fffffffffffffff0
- 10
```

> [!NOTE]
> Если `_ull_rshift` использовался параметр, то в случае отрицательного значения не было бы получено значение конца старшего смещенного сдвига, чтобы получить требуемый результат.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)
