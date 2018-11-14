---
title: __stosw
ms.date: 11/04/2016
f1_keywords:
- __stosw
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
ms.openlocfilehash: 4bfdf2191a4bf88ce6d061e1729e194236564330
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326424"
---
# <a name="stosw"></a>__stosw

**Блок, относящийся только к системам Microsoft**

Создает инструкцию строка магазина (`rep stosw`).

## <a name="syntax"></a>Синтаксис

```
void __stosw(
   unsigned short* Dest,
   unsigned short Data,
   size_t Count
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Целевой для операции.

*Данные*<br/>
[in] Сохраняемые данные.

*Количество*<br/>
[in] Длина блока слов для записи.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__stosw`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Результатом является то, что слово `Data` записывается в блок `Count` ключевые слова в `Dest` строку.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// stosw.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosw)

int main()
{
    unsigned short val = 128;
    unsigned short a[100];
    memset(a, 0, sizeof(a));
    __stosw(a+10, val, 2);
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);
}
```

```Output
0 128 128 0
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)