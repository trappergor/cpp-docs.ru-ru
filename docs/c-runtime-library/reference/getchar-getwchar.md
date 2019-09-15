---
title: getchar, getwchar
ms.date: 11/04/2016
api_name:
- getchar
- getwchar
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: b969dc48e949efa02b807ec0ea442da7cb793e15
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955414"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Считывает символ из стандартного входного потока.

## <a name="syntax"></a>Синтаксис

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Чтобы указать на ошибку чтения или конец файла, функция **GetChars** возвращает значение **EOF**, а **getwchar** возвращает **WEOF**. Для **GetChars**используйте **ferror** или **feof** для проверки ошибки или завершения файла.

## <a name="remarks"></a>Примечания

Каждая подпрограммы считывает один символ из **stdin** и увеличивает связанный указатель файла, чтобы он указывал на следующий символ. Функция **GetChars** аналогична [_fgetchar](fgetc-fgetwc.md), но реализована в виде функции и макроса.

Эти функции блокируют вызывающий поток, поэтому они потокобезопасны. Описание неблокирующей версии см. в разделе [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**getchar**|**getchar**|**getwchar**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getchar**|\<stdio.h>|
|**getwchar**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальная платформа Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**и **stderr**, должны быть перенаправляться до того, как функции времени выполнения C смогут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
