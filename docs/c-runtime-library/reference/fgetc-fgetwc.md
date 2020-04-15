---
title: fgetc, fgetwc
ms.date: 4/2/2020
api_name:
- fgetwc
- fgetc
- _o_fgetc
- _o_fgetwc
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
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: c1589c64127b47f4dd2a1147f2b4d549601db4fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347013"
---
# <a name="fgetc-fgetwc"></a>fgetc, fgetwc

Считывает символ из потока.

## <a name="syntax"></a>Синтаксис

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

**fgetc** возвращает символ, прочитанном как **Int,** или возвращает **EOF,** чтобы указать ошибку или конец файла. **fgetwc** возвращается, как [wint_t](../../c-runtime-library/standard-types.md), широкий символ, который соответствует символу читать или возвращает **WEOF,** чтобы указать на ошибку или конец файла. Для обеих функций используйте **feof** или **ferror,** чтобы различать ошибку и состояние конца файла. Если возникает ошибка чтения, то для потока устанавливается индикатор ошибки. Если *поток* **NULL,** **fgetc** и **fgetwc** вызывают недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции устанавливают **errno** к **EINVAL** и возвращают **EOF.**

## <a name="remarks"></a>Remarks

Каждая из этих функций считывает один символ из текущего положения файла, связанного с *потоком.* Функция затем увеличивает указатель связанного файла (если определен), чтобы он указывал на следующий символ. Если поток находится в конце файла, для него устанавливается индикатор конца файла.

**fgetc** эквивалентен **getc,** но реализуется только как функция, а не как функция и макрос.

**fgetwc** является широкохарактерный вариант **fgetc**; он читает **c** как мультибайтный символ или широкий символ в зависимости *от* того, поток открыт в текстовом режиме или двоичном режиме.

Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков.

Дополнительные сведения об обработке расширенных и многобайтовых символов в текстовом и двоичном режиме см. в разделе [Ввод-вывод в поток в кодировке Юникод в текстовом и двоичном режиме](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crt_fgetctxt"></a>Input: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Выходные данные

```Output
Line one.
Line two.
```

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
