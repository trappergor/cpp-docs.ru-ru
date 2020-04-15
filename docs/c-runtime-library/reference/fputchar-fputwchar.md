---
title: _fputchar, _fputwchar
ms.date: 4/2/2020
api_name:
- _fputchar
- _fputwchar
- _o__fputchar
- _o__fputwchar
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fputtchar
- _fputwchar
- fputwchar
- _fputtchar
- _fputchar
helpviewer_keywords:
- fputchar function
- standard output, writing to
- _fputtchar function
- fputwchar function
- _fputwchar function
- fputtchar function
- _fputchar function
ms.assetid: b92ff600-a924-4f2b-b0e7-3097ee31bdff
ms.openlocfilehash: 29d23dcaba75ad87b462a1a87c7a2ad9c8c7298b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346167"
---
# <a name="_fputchar-_fputwchar"></a>_fputchar, _fputwchar

Записывает символ в поток **stdout**.

## <a name="syntax"></a>Синтаксис

```C
int _fputchar(
   int c
);
wint_t _fputwchar(
   wchar_t c
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Символ, который требуется записать.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает записанный символ. Для **_fputchar**значение возврата **EOF** указывает на ошибку. Для **_fputwchar,** возвратное значение **WEOF** указывает на ошибку. Если c является **NULL,** эти функции генерируют недействительное исключение параметра, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, они возвращают **EOF** (или **WEOF)** и установить **errno** в **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Обе эти функции заражает один символ *c* для **stdout** и продвигает индикатор по мере необходимости. **_fputchar** эквивалентен `fputc( stdout )`. Это также эквивалентно **putchar**, но реализованы только в качестве функции, а не в качестве функции и макроса. В отличие от **fputc** и **putchar,** эти функции не совместимы со стандартом ANSI.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtchar**|**_fputchar**|**_fputchar**|**_fputwchar**|

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fputchar**|\<stdio.h>|
|**_fputwchar**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью –**stdin,** **stdout**и **stderr**— должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fputchar.c
// This program uses _fputchar
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
    char strptr[] = "This is a test of _fputchar!!\n";
    char *p = NULL;

    // Print line to stream using _fputchar.
    p = strptr;
    while( (*p != '\0') && _fputchar( *(p++) ) != EOF )
      ;
}
```

```Output
This is a test of _fputchar!!
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
