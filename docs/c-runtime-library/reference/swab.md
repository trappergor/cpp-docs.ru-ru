---
title: _swab
ms.date: 4/2/2020
api_name:
- _swab
- stdlib/_swab
- _o__swab
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: f7fe23cd9c1b2eab52ebe50904d0bb18fe16cea6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362958"
---
# <a name="_swab"></a>_swab

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

Функция **мазка** не возвращает значение. Функция устанавливает **errno** к **EINVAL,** если либо *src* или *dest* указатель является нулевым или *n* меньше нуля, и недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md)

Подробнее об этом и других кодах возврата читайте [_doserrno, errno, _sys_errlist и _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Remarks

Если *n* четно, **то _swab** функция копий *n* байтов от *src,* обменивает каждую пару смежных байтов, и хранит результат на *dest.* Если *n* является нечетным, **_swab** копии и свопы первые *n*-1 байт *src*, и окончательный байт не скопирован. Функция **_swab** обычно используется для подготовки двоичных данных для передачи на машину, используюую другой порядок байта.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
