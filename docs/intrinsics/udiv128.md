---
title: _udiv128
ms.date: 04/17/2019
f1_keywords:
- _udiv128
helpviewer_keywords:
- _udiv128 intrinsic
ms.openlocfilehash: 0e66bbe978199f47134aa288bdd2bac4eb3e332a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390169"
---
# <a name="udiv128"></a>_udiv128

`_udiv128` Внутренние делит 128-разрядного целого числа без знака, по 64-разрядное целое число без знака. Возвращаемое значение содержит частное, и функция возвращает остаток в качестве параметра указатель. `_udiv128` — **системам Microsoft**.

## <a name="syntax"></a>Синтаксис

```C
unsigned __int64 _udiv128(
   unsigned __int64 highDividend,
   unsigned __int64 lowDividend,
   unsigned __int64 divisor,
   unsigned __int64 *remainder
);
```

### <a name="parameters"></a>Параметры

*highDividend* \
[in] Старшие 64 разряда делимого.

*lowDividend* \
[in] Младшие 64 разряда делимого.

*Делитель* \
[in] 64-разрядное целое число необходимо разделить.

*Остаток* \
[out] 64-разрядное целое число битов остатка.

## <a name="return-value"></a>Возвращаемое значение

64 разряда частного.

## <a name="remarks"></a>Примечания

Передайте верхний 64 разряда 128-разрядный делимое в *highDividend*, а нижние 64 бита в *lowDividend*. Встроенная делит значение на *делитель*. Она сохраняет остаток в 64-разрядного целого числа без знака, на которые указывают *остаток*и возвращает 64 разряда частного.

`_udiv128` Встроенная является доступен, начиная с Visual Studio RTM 2019 г.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_udiv128`|X64|\<immintrin.h>|

## <a name="see-also"></a>См. также

[_div128](div128.md) \
[Встроенные объекты компилятора](compiler-intrinsics.md)
