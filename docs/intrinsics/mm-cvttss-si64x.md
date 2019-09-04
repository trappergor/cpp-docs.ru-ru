---
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: 69016a4e23b020b2c4c79c6b97a5a76f2b2dc028
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217413"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Блок, относящийся только к системам Microsoft**

Выдает расширенную версию x64 инструкции CONVERT с плавающей запятой одиночной точности до 64-разрядного целого числа (`cvttss2si`).

## <a name="syntax"></a>Синтаксис

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Параметры

*value*\
окне Структура `__m128` , содержащая значения с плавающей точкой одиночной точности.

## <a name="return-value"></a>Возвращаемое значение

Результат преобразования первого значения с плавающей запятой в 64-разрядное целое число.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Внутренняя функция отличается от `_mm_cvtss_si64x` того, что неточные преобразования усекаются в сторону нуля. `__m128` Поскольку структура представляет регистр XMM, созданная инструкция перемещает данные из регистра XMM в системную память.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__m128](../cpp/m128.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
