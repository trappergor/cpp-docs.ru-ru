---
title: putc, putwc
ms.date: 11/04/2016
apiname:
- putwc
- putc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 05bbb5434e6626076aab0d574b04058ec730b77c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444699"
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

*c*<br/>
Символ, который требуется записать.

*поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

Возвращает записанный символ. Чтобы указать ошибку или конец файла, **putc** и **putchar** возвращают ** EOF`; **putwc` и **putwchar** возвращают **WEOF**. Для всех четырех подпрограмм используйте [ferror](ferror.md) или [feof](feof.md) для проверки наличия ошибки или конца файла. Если передан пустой указатель *поток*, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EOF** или **WEOF** и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Putc** подпрограмма записывает отдельный символ *c* в выходные данные *поток* в текущей позиции. Любое целое число может быть передан **putc**, но записываются только младшие 8 битов. **Putchar** подпрограмма идентична `putc( c, stdout )`. Если возникает ошибка чтения, то в каждой подпрограмме для каждого потока устанавливается индикатор ошибки. **putc** и **putchar** аналогичны **fputc** и **_fputchar**, соответственно, но реализованы и как функции и как макросы (см. в разделе [ Выбор между функциями и макросами](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). **putwc** и **putwchar** представляют собой двухбайтовые версии **putc** и **putchar**, соответственно. **putwc** и **putc** ведут себя одинаково, если поток открыт в режиме ANSI. **putc** сейчас не поддерживает выходные данные в поток в кодировке Юникод.

Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков. Дополнительные сведения см. в разделе **_putc_nolock, _putwc_nolock**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

### <a name="output"></a>Вывод

```Output
This is the line of output
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
