---
title: fgetc, fgetwc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fgetwc
- fgetc
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
- _fgettc
- fgetwc
- fgetc
dev_langs:
- C++
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82db726bc0296027536798771680cc1326fc00df
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

**fgetc** возвращает символ, считанный как **int** или возвращает **EOF** для отображения ошибки или конца файла. **fgetwc** возвращает, как [wint_t](../../c-runtime-library/standard-types.md), расширенный символ, который соответствует прочитанному символу или возвращает **WEOF** для отображения ошибки или конца файла. Для обеих функций следует использовать **feof** или **ferror** различать ошибки и конец файла. Если возникает ошибка чтения, то для потока устанавливается индикатор ошибки. Если *поток* — **NULL**, **fgetc** и **fgetwc** вызывают обработчик недопустимого параметра, как описано в [параметр Проверка](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **EOF**.

## <a name="remarks"></a>Примечания

Каждая из этих функций считывает один символ из текущей позиции файла, связанного с *поток*. Функция затем увеличивает указатель связанного файла (если определен), чтобы он указывал на следующий символ. Если поток находится в конце файла, для него устанавливается индикатор конца файла.

**fgetc** эквивалентно **getc**, но реализуется только как функция, а не как функция и макрос.

**fgetwc** — это двухбайтовая версия **fgetc**; она считывает **c** как Многобайтовый или расширенный символ согласно ли *поток* открыт в текстовом или двоичном режиме.

Версии с суффиксом **_nolock** идентичны за исключением того, что они не защищены от помех со стороны других потоков.

Дополнительные сведения об обработке расширенных и многобайтовых символов в текстовом и двоичном режиме см. в разделе [Ввод-вывод в поток в кодировке Юникод в текстовом и двоичном режиме](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="input-crtfgetctxt"></a>Input: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Line one.
Line two.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
