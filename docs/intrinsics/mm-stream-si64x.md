---
title: _mm_stream_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_si64x
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
ms.openlocfilehash: d7f7a75be1602fbb70a230b0dd3a791be99d092a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039602"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Блок, относящийся только к системам Microsoft**

Создает инструкция movnti. Записывает данные `Source` в расположении памяти, заданном параметром `Dest`, не засоряя кэши.

## <a name="syntax"></a>Синтаксис

```
void _mm_stream_si64x(
   __int64 * Dest,
   __int64 Source
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Указатель на расположение для записи исходных данных.

*Исходный код*<br/>
[in] Данные для записи.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_mm_stream_si64x`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)