---
title: _mm_cvttss_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: 5c2dd98ad3f74ac56b3656ac5f6f450efc40c088
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522984"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x

**Блок, относящийся только к системам Microsoft**

Выдает x64 расширенной версии функции Convert с усечение числа с плавающей запятой одиночной точности в 64-битовое целое число (`cvttss2si`) инструкции.

## <a name="syntax"></a>Синтаксис

```
__int64 _mm_cvttss_si64x( 
   __m128 value 
);
```

#### <a name="parameters"></a>Параметры

*значение*<br/>
[in] `__m128` Структуру, содержащую значения с плавающей запятой одиночной точности.

## <a name="return-value"></a>Возвращаемое значение

Результат преобразования первое значение с плавающей запятой в 64-битовое целое число.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_cvttss_si64x`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Встроенная отличается от `_mm_cvtss_si64x` только в том, что неточный преобразования усеченное в сторону нуля. Так как `__m128` структура представляет регистр XMM, создается инструкция перемещает данные из регистр XMM в оперативной памяти.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
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

[__m128](../cpp/m128.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)