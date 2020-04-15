---
title: putc, putwc
ms.date: 4/2/2020
api_name:
- putwc
- putc
- _o_putc
- _o_putwc
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
- _puttc
- putwc
- putc
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
ms.openlocfilehash: 8809595c90c48976d9f28ffa659714f5b9d919c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338461"
---
# <a name="putc-putwc"></a>putc, putwc

Записывает символ в поток.

## <a name="syntax"></a>Синтаксис

```C
int putc(
   int c,
   FILE *stream
);
wint_t putwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Символ, который требуется записать.

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает записанный символ. Чтобы указать ошибку или состояние конца файла, **putc** и **putchar** возврат **EOF;** **putwc** и **putwchar** возвращение **WEOF**. Для всех четырех подпрограмм используйте [ferror](ferror.md) или [feof](feof.md) для проверки наличия ошибки или конца файла. Если пройден нулевой указатель для *потока,* недействительный обработчик параметров вызывается, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции возвращают **EOF** или **WEOF** и устанавливают **errno** **в EINVAL.**

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Рутина **putc** записывает один символ *c* к *выходному потоку* в текущем положении. Любой целью может быть передан **в putc,** но только нижние 8 битов написаны. **Путчар** рутина идентична `putc( c, stdout )`. Если возникает ошибка чтения, то в каждой подпрограмме для каждого потока устанавливается индикатор ошибки. **putc** и **putchar** похожи на **fputc** и **_fputchar,** соответственно, но реализуются как функции, так и в качестве макросов (см. [Выбор между функциями и макросом).](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md) **putwc** и **putwchar** являются широкохарактерными версиями **putc** и **putchar,** соответственно. **putwc** и **putc** ведут себя одинаково, если поток открыт в режиме ANSI. в настоящее время **putc** не поддерживает выход в поток UNICODE.

Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков. Дополнительные сведения см. в разделе **_putc_nolock, _putwc_nolock**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью, **stdin,** **stdout**и **stderr,** должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_putc.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putc( *p, stream );
}
```

### <a name="output"></a>Выходные данные

```Output
This is the line of output
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
