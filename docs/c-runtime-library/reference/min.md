---
title: __min | Документы Майкрософт
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __min
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __min
- min
- _min
dev_langs:
- C++
helpviewer_keywords:
- __min macro
- min macro
- minimum macro
- _min macro
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cc69cb018cda6fc093c570dab86a8df4cf396b7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="min"></a>__min

Макрос препроцессора, который возвращает меньшее из двух значений.

## <a name="syntax"></a>Синтаксис

```C
#define __min(a,b) (((a) < (b)) ? (a) : (b))
```

### <a name="parameters"></a>Параметры

*a*, *b*<br/>
Значения любого типа, **<** занимается оператор.

## <a name="return-value"></a>Возвращаемое значение

Меньший из двух аргументов.

## <a name="remarks"></a>Примечания

**__Min** макрос сравнивает два значения и возвращает значение меньшего. Аргументы могут быть любого числового типа данных со знаком или без знака. Оба аргумента и возвращаемое значение должны принадлежать к одному типу данных.

Аргумента, возвращаемого вычисляется дважды макросом. Это может привести к непредвиденным результатам, если аргумент представляет собой выражение, изменяет его значение, когда оно вычисляется, такие как `*p++`.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**__min**|\<stdlib.h>|

## <a name="example"></a>Пример

```C
// crt_minmax.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int a = 10;
   int b = 21;

   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );
}
```

```Output
The larger of 10 and 21 is 21
The smaller of 10 and 21 is 10
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
[__max](max.md)<br/>
