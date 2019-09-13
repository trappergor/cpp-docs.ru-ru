---
title: _mm_cvtsi64x_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 0e9bacc56f212e804467d1c6e0159a1749235976
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217458"
---
# <a name="_mm_cvtsi64x_ss"></a>_mm_cvtsi64x_ss

**Блок, относящийся только к системам Microsoft**

Создает расширенную версию 64-разрядной версии преобразования 64 бит в скалярную инструкцию значения с плавающей запятой`cvtsi2ss`одиночной точности ().

## <a name="syntax"></a>Синтаксис

```C
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

### <a name="parameters"></a>Параметры

*конкретного*\
окне Структура `__m128` , содержащая четыре значения с плавающей запятой одиночной точности.

*&* \
окне 64-разрядное целое число, которое преобразуется в значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

`__m128` Структура, первое значение с плавающей запятой которой является результатом преобразования. Остальные три значения копируются без изменений из.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Структура представляет регистр XMM, поэтому встроенное позволяет переместить значение b из системной памяти в регистр XMM. `__m128`

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__m128](../cpp/m128.md)\
[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
