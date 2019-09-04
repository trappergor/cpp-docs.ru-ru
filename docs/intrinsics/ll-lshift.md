---
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 158ecbf39320d70b51f1f498a0b689ba58fec363
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221820"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Блок, относящийся только к системам Microsoft**

Сдвигает переданное 64-разрядное значение влево на указанное число битов.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>Параметры

*Виде*\
окне 64-разрядное целочисленное значение, которое необходимо сдвинуть влево.

*нбит*\
окне Число битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Маска, смещенная влево по `nBit` битам.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Если вы компилируете программу для 64-разрядной архитектуры и `nBit` превышает 63, число битов для сдвига — `nBit` остаток от деления по модулю 64. Если вы компилируете программу для 32-разрядной архитектуры и `nBit` превышает 31, число битов для сдвига является `nBit` остатком по модулю 32.

В имени указывает, что это операция над `long long` (`__int64`). `ll`

## <a name="example"></a>Пример

```cpp
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>Вывод

```Output
10000
```

> [!NOTE]
> Нет неподписанной версии операции сдвига влево. Это вызвано `__ll_lshift` тем, что уже использует входной параметр без знака. В отличие от сдвига вправо, не существует зависимости от знака сдвига влево, так как наименьший значащий бит в результате всегда имеет нулевое значение, независимо от знака сдвига значения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__ll_rshift](../intrinsics/ll-rshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
