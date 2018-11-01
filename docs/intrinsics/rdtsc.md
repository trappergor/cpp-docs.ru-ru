---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 5f058eaf6587b74f5a75044416d23ac6b64fb415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582069"
---
# <a name="rdtsc"></a>__rdtsc

**Блок, относящийся только к системам Microsoft**

Создает `rdtsc` инструкция, которая возвращает метку времени процессора. Метка времени процессора регистрирует число тактов с момента последнего сброса.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Возвращаемое значение

64-разрядное целое число без знака, представляющее счетчик тактов.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная.

Интерпретация TSC значения в этом поколении оборудования отличается от более ранних версий x64. См. в разделе руководства оборудования, Дополнительные сведения.

## <a name="example"></a>Пример

```
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)