---
title: __ull_rshift
ms.date: 09/02/2019
f1_keywords:
- __ull_rshift
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
ms.openlocfilehash: e914a019877482058c6b2842d3138cda02f1e228
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219707"
---
# <a name="__ull_rshift"></a>__ull_rshift

**Блок, относящийся только к системам Microsoft**

в x64 сдвигает 64-разрядное значение, заданное первым параметром, вправо на число битов, заданное вторым параметром.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __ull_rshift(
   unsigned __int64 mask, 
   int nBit
);
```

### <a name="parameters"></a>Параметры

*виде*\
окне 64-разрядное целочисленное значение, которое нужно сдвинуть вправо.

*нбит*\
окне Число битов для сдвига, остаток от деления 32 на x86 и по модулю 64 на x64.

## <a name="return-value"></a>Возвращаемое значение

Маска, смещенная по `nBit` битам.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__ull_rshift`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Если второй параметр больше 31 для x86 (63 в x64), то это число берется по модулю 32 (64 в x64), чтобы определить число битов для сдвига. В имени указывается `unsigned long long (unsigned __int64)`. `ull`

## <a name="example"></a>Пример

```cpp
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

```Output
1
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__ll_lshift](../intrinsics/ll-lshift.md)\
[__ll_rshift](../intrinsics/ll-rshift.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
