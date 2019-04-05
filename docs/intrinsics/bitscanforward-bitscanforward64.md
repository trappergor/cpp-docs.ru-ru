---
title: _BitScanForward, _BitScanForward64
ms.date: 11/04/2016
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 8b09aeee485611ddd20d51b4c1e36ec98c03c26e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022571"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Блок, относящийся только к системам Microsoft**

Поиск данных маски от наименьшего значащего разряда (LSB) к наибольшему значащему разряду (MSB) для значащего разряда (1).

## <a name="syntax"></a>Синтаксис

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>Параметры

*Индекс*<br/>
[out] Загрузить с позиции разряда Первый значащий разряд (1) найден.

*Маска*<br/>
[in] 32-разрядная или 64-разрядное значение для поиска.

## <a name="return-value"></a>Возвращаемое значение

0, если маска равна нулю; ненулевое значение в противном случае.

## <a name="remarks"></a>Примечания

Если найден значащий разряд, положение разряда первого найденного значащего разряда возвращается в качестве первого параметра. Если значащий разряд не найден, возвращается 0; в противном случае возвращается 1.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_BitScanForward`|x86, ARM, x64|
|`_BitScanForward64`|ARM, x64|

**Файл заголовка** \<intrin.h >

## <a name="example"></a>Пример

```
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>Входные данные

```
12
```

## <a name="sample-output"></a>Пример результатов выполнения

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)