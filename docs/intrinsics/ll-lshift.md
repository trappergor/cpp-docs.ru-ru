---
title: __ll_lshift
ms.date: 11/04/2016
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 5a91ce5db46b19be570f8d48a584a2caeabcc163
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024469"
---
# <a name="lllshift"></a>__ll_lshift

**Блок, относящийся только к системам Microsoft**

Сдвигает указанное значение 64-разрядных влево на указанное число битов.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

#### <a name="parameters"></a>Параметры

*Маска*<br/>
[in] 64-разрядное целое значение для сдвига влево.

*nBit*<br/>
[in] Количество битов для сдвига.

## <a name="return-value"></a>Возвращаемое значение

Маска сдвинуты влево на `nBit` bits.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__ll_lshift`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

При компиляции программы с помощью 64-разрядной архитектуры и `nBit` больше, чем 63, количество битов для сдвига `nBit` берется по модулю 64. При компиляции программы с помощью 32-разрядной архитектуры и `nBit` больше, чем 31, количество битов для сдвига `nBit` остаток от деления 32.

`ll` В имени указывает, что эта операция выполняется в на `long long` (`__int64`).

## <a name="example"></a>Пример

```
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>Вывод

```
10000
```

**Примечание** отсутствует версия без знака операции сдвига влево. Это обусловлено `__ll_lshift` уже использует без знака входного параметра. В отличие от сдвига вправо отсутствует зависимость входа для сдвига влево, потому что младший значащий бит в результате всегда равно нулю независимо от знака сдвиг значения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[__ull_rshift](../intrinsics/ull-rshift.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)