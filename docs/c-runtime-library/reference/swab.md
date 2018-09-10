---
title: _swab | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2975e63f79818e5eac430056258b72b9c6641a49
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100278"
---
# <a name="swab"></a>_swab

Меняет местами байты.

## <a name="syntax"></a>Синтаксис

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Параметры

*src*<br/>
Данные, которые следует скопировать и поменять местами.

*dest*<br/>
Место хранения для переставленных местами данных.

*n*<br/>
Число байтов, которые следует скопировать и поменять местами.

## <a name="return-value"></a>Возвращаемое значение

**Swab** функция не возвращает значение. Функция задает **errno** для **EINVAL** Если *src* или *dest* указатель имеет значение null или *n* меньше нуля, и недопустимого параметра вызывается обработчик, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Если *n* четное, **_swab** функции копий *n* байтов из *src*, меняет местами каждого соседние пары байтов и сохраняет результат в *dest*. Если *n* является нечетным, **_swab** копирует и меняет местами первые *n*-1 байт *src*, и последний байт не копируется. **_Swab** функция обычно используется для подготовки двоичных данных для передачи на компьютер, который использует другой порядок байтов.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>См. также

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
