---
title: __movsd
ms.date: 11/04/2016
f1_keywords:
- __movsd
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
ms.openlocfilehash: 6760904f4eaa6ee32cf9326638ab68f728db45d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628596"
---
# <a name="movsd"></a>__movsd

**Блок, относящийся только к системам Microsoft**

Создает строку переместить (`rep movsd`) инструкции.

## <a name="syntax"></a>Синтаксис

```
void __movsd( 
   unsigned long* Dest, 
   unsigned long* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Целевой для операции.

*Источник*<br/>
[in] Источник операции.

*Количество*<br/>
[in] Число двойных слов для копирования.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__movsd`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

В результате первый `Count` двойных слов, на которые указывают `Source` копируются `Dest` строка.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)