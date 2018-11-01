---
title: __stosq
ms.date: 11/04/2016
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 48c3e8db2683ee190a23974d12d36fbeef6a0094
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477471"
---
# <a name="stosq"></a>__stosq

**Блок, относящийся только к системам Microsoft**

Создает инструкцию строка магазина (`rep stosq`).

## <a name="syntax"></a>Синтаксис

```
void __stosb( 
   unsigned __int64* Dest, 
   unsigned __int64 Data, 
   size_t Count 
);
```

#### <a name="parameters"></a>Параметры

*dest*<br/>
[out] Целевой для операции.

*Данные*<br/>
[in] Сохраняемые данные.

*Количество*<br/>
[in] Длина блока учетверенных слова для записи.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__stosq`|AMD64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Результатом является то, что quadword `Data` записывается в блок `Count` учетверенных слова в `Dest` строку.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// stosq.c
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosq)

int main()
{
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;
   unsigned __int64 a[10];
   memset(a, 0, sizeof(a));
   __stosq(a+1, val, 2);
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

## <a name="output"></a>Вывод

```
0 ffffffffffff ffffffffffff 0
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)