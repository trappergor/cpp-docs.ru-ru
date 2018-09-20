---
title: _bittest _bittest64 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _bittest64
- _bittest_cpp
- _bittest64_cpp
- _bittest
dev_langs:
- C++
helpviewer_keywords:
- _bittest intrinsic
- _bittest64 intrinsic
- bt instruction
ms.assetid: 15e62afb-abea-4ee7-a6b1-13efa2034937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8057653188d46fd627ba5d031be8b50d2d8e7108
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418233"
---
# <a name="bittest-bittest64"></a>_bittest, _bittest64

**Блок, относящийся только к системам Microsoft**

Создает инструкцию `bt`, которая проверяет разряд в позиции `b` адреса `a` и возвращает значение разряда.

## <a name="syntax"></a>Синтаксис

```
unsigned char _bittest(
   long const *a,
   long b
);
unsigned char _bittest64(
   __int64 const *a,
   __int64 b
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
[in] Указатель памяти для проверки.

*b*<br/>
[in] Позиция разряда для тестирования.

### <a name="return-value"></a>Возвращаемое значение

Разряд на указанной позиции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_bittest`|x86, ARM, x64|\<Intrin.h >|
|`_bittest64`|ARM, x64|\<Intrin.h >|

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```cpp
// bittest.cpp
// processor: x86, ARM, x64

#include <stdio.h>
#include <intrin.h>

long num = 78002;

int main()
{
    unsigned char bits[32];
    long nBit;

    printf_s("Number: %d\n", num);

    for (nBit = 0; nBit < 31; nBit++)
    {
        bits[nBit] = _bittest(&num, nBit);
    }

    printf_s("Binary representation:\n");
    while (nBit--)
    {
        if (bits[nBit])
            printf_s("1");
        else
            printf_s("0");
    }
}
```

```Output
Number: 78002
Binary representation:
0000000000000010011000010110010
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)