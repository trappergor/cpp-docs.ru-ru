---
title: __getcallerseflags
ms.date: 11/04/2016
f1_keywords:
- _getcallerseflags
- _getcallerseflags_cpp
helpviewer_keywords:
- _getcallerseflags intrinsic
ms.assetid: 2386596f-33aa-4cc7-b026-5a834637270a
ms.openlocfilehash: a2df7087c605882340da16f56dae2e991c5d7dd1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039943"
---
# <a name="getcallerseflags"></a>__getcallerseflags

**Блок, относящийся только к системам Microsoft**

Возвращает значение EFLAGS из контекста вызывающей стороны.

## <a name="syntax"></a>Синтаксис

```
unsigned int __getcallerseflags(void);
```

## <a name="return-value"></a>Возвращаемое значение

Значение EFLAGS из контекста вызывающей стороны.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__getcallerseflags`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// getcallerseflags.cpp
// processor: x86, x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__getcallerseflags)

unsigned int g()
{
    unsigned int EFLAGS = __getcallerseflags();
    printf_s("EFLAGS 0x%x\n", EFLAGS);
    return EFLAGS;
}
unsigned int f()
{
    return g();
}

int main()
{
    unsigned int i;
    i = f();
    i = g();
    return 0;
}
```

```Output
EFLAGS 0x202
EFLAGS 0x206
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)