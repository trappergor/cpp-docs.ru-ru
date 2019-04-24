---
title: _mm_cvtsi64x_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 3ba9dc56cbb027e8cf9f31d293b3f96908aff5e4
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039784"
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss

**Блок, относящийся только к системам Microsoft**

Создает x64 расширенной версии преобразование 64-разрядное целое число, чтобы скалярное значение с плавающей запятой одиночной точности (`cvtsi2ss`) инструкции.

## <a name="syntax"></a>Синтаксис

```
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in] `__m128` Структуру, содержащую четыре значения с плавающей запятой одиночной точности.

*b*<br/>
[in] 64-разрядное целое, преобразуемое в значение с плавающей запятой.

## <a name="return-value"></a>Возвращаемое значение

`__m128` Структуры, первый с плавающей запятой, значение которого является результатом преобразования. Другие три значения, без изменений копируются из `a`.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`__m128` Структура представляет регистр XMM, поэтому эта встроенная функция допускает указание значения `b` системной памяти для перехода в регистров XMM можно зарегистрировать.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
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

[__m128](../cpp/m128.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)