---
title: _div64
ms.date: 04/17/2019
f1_keywords:
- _div64
helpviewer_keywords:
- _div64 intrinsic
ms.openlocfilehash: a221cc7cf0655a41873c6777aecd8a9b27131b74
ms.sourcegitcommit: 2ce88de75e7681220ae09a0ab13056f22f357a46
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59982423"
---
# <a name="div64"></a>_div64

`_div64` Внутренние делит 64-разрядное целое число, 32-разрядное целое число. Возвращаемое значение содержит частное, и функция возвращает остаток в качестве параметра указатель. `_div64` — **системам Microsoft**.

## <a name="syntax"></a>Синтаксис

```C
int _div64(
   __int64 dividend,
   int divisor,
   int* remainder
);
```

### <a name="parameters"></a>Параметры

*Делимое* \
[in] 64-разрядное целое число, разделить.

*Делитель* \
[in] 32-разрядное целое число необходимо разделить.

*Остаток* \
[out] 32-разрядное целое число битов остатка.

## <a name="return-value"></a>Возвращаемое значение

32 бита частного.

## <a name="remarks"></a>Примечания

`_div64` Внутренние разделяет *делимое* по *делитель*. Она сохраняет остаток в 32-разрядное целое число, на которые указывают *остаток*и возвращает частное 32 разряда.

`_div64` Встроенная является доступен, начиная с Visual Studio RTM 2019 г.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_div64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>См. также

[_udiv64](udiv64.md) \
[Встроенные объекты компилятора](compiler-intrinsics.md)
