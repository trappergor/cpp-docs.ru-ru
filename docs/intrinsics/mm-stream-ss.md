---
title: _mm_stream_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 76c6c848351df773b9857b2f83726b64db982d9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263234"
---
# <a name="mmstreamss"></a>_mm_stream_ss

**Блок, относящийся только к системам Microsoft**

Записывает 32-разрядные данные в ячейку памяти не засоряя кэши.

## <a name="syntax"></a>Синтаксис

```
void _mm_stream_ss(
   float * Dest,
   __m128 Source
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Указатель на расположение, куда будут записываться исходных данных.

*Источник*<br/>
[in] 128-разрядное число, которое содержит `float` значение для записи в его нижней 32 бита...

## <a name="return-value"></a>Возвращаемое значение

Отсутствует.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция создает `movntss` инструкции. Чтобы определить аппаратная поддержка для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит равен 1, если инструкция поддерживается и 0 в противном случае.

При выполнении кода, использующего `_mm_stream_ss` встроенные на оборудовании, которое не поддерживает `movntss` инструкции, результаты будут непредсказуемыми.

## <a name="example"></a>Пример

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**Завершение блока, относящегося только к системам Майкрософт**

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)<br/>
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)<br/>
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)