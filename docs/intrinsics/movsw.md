---
title: __movsw
ms.date: 11/04/2016
f1_keywords:
- __movsw
helpviewer_keywords:
- movsw instruction
- rep movsw instruction
- __movsw intrinsic
ms.assetid: db402ad5-7f0e-449a-b0b0-eea9928d6435
ms.openlocfilehash: be80a7f50a62146ffcd6d271def6d254da5a88b2
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51329869"
---
# <a name="movsw"></a>__movsw

**Блок, относящийся только к системам Microsoft**

Создает строку переместить (`rep movsw`) инструкции.

## <a name="syntax"></a>Синтаксис

```
void __movsw(
   unsigned short* Dest,
   unsigned short* Source,
   size_t Count
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Целевой для операции.

*Источник*<br/>
[in] Источник операции.

*Количество*<br/>
[in] Число слов для копирования.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__movsw`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

В результате первый `Count` слов, на которые указывают `Source` копируются `Dest` строка.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// movsw.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsw)

int main()
{
    unsigned short s1[10];
    unsigned short s2[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
    __movsw(s1, s2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", s1[i]);
    printf_s("\n");
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)