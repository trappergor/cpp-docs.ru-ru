---
title: __movsq
ms.date: 11/04/2016
f1_keywords:
- __movsq
helpviewer_keywords:
- __movsq intrinsic
- rep movsq instruction
- movsq instruction
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
ms.openlocfilehash: 06f42befa24d4024b3ad4b0c0a8d0897cb2aee9b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326372"
---
# <a name="movsq"></a>__movsq

**Блок, относящийся только к системам Microsoft**

Создает повторяющиеся строки перемещения (`rep movsq`) инструкции.

## <a name="syntax"></a>Синтаксис

```
void __movsq(
   unsigned char* Dest,
   unsigned char* Source,
   size_t Count
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Целевой для операции.

*Источник*<br/>
[in] Источник операции.

*Количество*<br/>
[in] Число учетверенных слова для копирования.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__movsq`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

В результате первый `Count` учетверенных слова, на которые указывают `Source` копируются `Dest` строка.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// movsq.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsq)

int main()
{
    unsigned __int64 a1[10];
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,
                               150, 50};
    __movsq(a1, a2, 10);

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