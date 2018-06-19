---
title: _fgetchar, _fgetwchar | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fgetchar
- _fgetwchar
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
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
dev_langs:
- C++
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87b5b42c72f4ea2756358208f85d9c01f7863dba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32400568"
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar

Считывает символ из **stdin**.

## <a name="syntax"></a>Синтаксис

```C
int _fgetchar( void );
wint_t _fgetwchar( void );
```

## <a name="return-value"></a>Возвращаемое значение

**_fgetchar** возвращает символ, считанный как **int** или возвращать **EOF** для отображения ошибки или конца файла. **_ *** fgetwchar** возвращает, как [wint_t](../../c-runtime-library/standard-types.md), расширенный символ, который соответствует прочитанному символу или возвращает **WEOF** для отображения ошибки или конца файла. Для обеих функций следует использовать **feof** или **ferror** различать ошибки и конец файла.

## <a name="remarks"></a>Примечания

Эти функции производят чтение из одного символа **stdin**. Функция затем увеличивает указатель связанного файла (если определен), чтобы он указывал на следующий символ. Если поток находится в конце файла, для него устанавливается индикатор конца файла.

**_fgetchar** эквивалентно `fgetc( stdin )`. Кроме того, это эквивалентно **getchar**, но реализован только как функция, а не как функция и макрос. **_fgetwchar** — это двухбайтовая версия **_fgetchar**.

Эти функции не совместимы со стандартом ANSI.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fgettchar**|**_fgetchar**|**_fgetchar**|**_fgetwchar**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fgetchar**|\<stdio.h>|
|**_fgetwchar**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, связанные с консолью —**stdin**, **stdout**, и **stderr**— необходимо перенаправить, чтобы функции времени выполнения C их можно использовать в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_fgetchar.c
// This program uses _fgetchar to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char buffer[81];
   int  i, ch;

   // Read in first 80 characters and place them in "buffer":
   ch = _fgetchar();
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = _fgetchar();
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
}
```

```Output

      Line one.
Line two.Line one.
Line two.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fputc, fputwc](fputc-fputwc.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
