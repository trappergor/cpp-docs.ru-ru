---
title: _mm_stream_sd
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: 3555b71e15d6f9c618a83f573d6da3cda9e7b705
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263247"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Блок, относящийся только к системам Microsoft**

Записывает 64-разрядные данные в ячейку памяти не засоряя кэши.

## <a name="syntax"></a>Синтаксис

```
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Указатель на расположение, куда будет записан исходных данных.

*Источник*<br/>
[in] 128-разрядным значением, содержащим `double` значение для записи в его нижней 64 бита...

## <a name="return-value"></a>Возвращаемое значение

Отсутствует.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция создает `movntsd` инструкции. Чтобы определить аппаратная поддержка для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 6 `CPUInfo[2] (ECX)`. Этот бит равен 1, если оборудование поддерживает Эта инструкция и 0 в противном случае.

При выполнении кода, использующего `_mm_stream_sd` встроенные на оборудовании, которое не поддерживает `movntsd` инструкции, результаты будут непредсказуемыми.

## <a name="example"></a>Пример

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128d vals;
    double d[2];

    d[0] = -1.;
    d[1] = -2.;
    vals.m128d_f64[0] = 0.;
    vals.m128d_f64[1] = 1.;
    _mm_stream_sd(&d[1], vals);
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;
}
```

```Output
d[0] = -1, d[1] = 1
```

**Завершение блока, относящегося только к системам Майкрософт**

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)<br/>
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)