---
title: _mm_cvtss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: 6079ed7846a35ff16355f0341d63430f9846057f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217432"
---
# <a name="_mm_cvtss_si64x"></a>_mm_cvtss_si64x

**Блок, относящийся только к системам Microsoft**

Создает расширенную версию 64-разрядной`cvtss2si`версии преобразования скалярного числа с плавающей запятой с одинарной точностью до 64.

## <a name="syntax"></a>Синтаксис

```C
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Параметры

*value*\
окне Структура `__m128` , содержащая плавающие значения типа Point.

## <a name="return-value"></a>Возвращаемое значение

64-разрядное целое число, результат преобразования первого значения с плавающей запятой в целое число.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_cvtss_si64x`|X64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Первый элемент значения структуры преобразуется в целое число и возвращается. Биты управления округлением в МКСКСР используются для определения поведения округления. По умолчанию используется режим округления с округлением до ближайшего значения, округление до четного числа, если десятичная часть равна 0,5. `__m128` Поскольку структура представляет регистр XMM, встроенная функция принимает значение из регистра XMM и записывает его в системную память.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__m128d](../cpp/m128d.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
