---
title: _udiv64
ms.date: 04/17/2019
f1_keywords:
- _udiv64
helpviewer_keywords:
- _udiv64 intrinsic
ms.openlocfilehash: 73a29b180eeda49a9a25e9e568d25c7563234fad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390156"
---
# <a name="udiv64"></a>_udiv64

`_udiv64` Внутренние делит 64-разрядного целого числа без знака, по 32-разрядное целое число без знака. Возвращаемое значение содержит частное, и функция возвращает остаток в качестве параметра указатель. `_udiv64` — **системам Microsoft**.

## <a name="syntax"></a>Синтаксис

```C
unsigned int _udiv64(
   unsigned __int64 dividend,
   unsigned int divisor,
   unsigned int* remainder
);
```

### <a name="parameters"></a>Параметры

*Делимое*<br/>
[in] 64-разрядное целое число без знака для деления.

*Делитель*<br/>
[in] 32-разрядное целое число без знака деления.

*remainder*<br/>
[out] Остаток 32-разрядного целого числа без знака.

## <a name="return-value"></a>Возвращаемое значение

32 бита частного.

## <a name="remarks"></a>Примечания

`_udiv64` Внутренние разделяет *делимое* по *делитель*. Она сохраняет остаток в 32-разрядного целого числа без знака, на которые указывают *остаток*и возвращает частное 32 разряда.

`_udiv64` Встроенная является доступен, начиная с Visual Studio RTM 2019 г.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_udiv64`|x86, x64|\<immintrin.h>|

## <a name="see-also"></a>См. также

[_div64](div64.md) \
[Встроенные объекты компилятора](compiler-intrinsics.md)
