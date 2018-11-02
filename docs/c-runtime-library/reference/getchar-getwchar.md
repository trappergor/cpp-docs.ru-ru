---
title: getchar, getwchar
ms.date: 11/04/2016
apiname:
- getchar
- getwchar
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
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: 5f8d7dbeb35c8818706eb6070df613df8654feb6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626607"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Считывает символ из стандартного входного потока.

## <a name="syntax"></a>Синтаксис

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Чтобы указать на ошибку чтения или конец файла, **getchar** возвращает **EOF**, и **getwchar** возвращает **WEOF**. Для **getchar**, использовать **ferror** или **feof** для проверки наличия ошибки или достижение конца файла.

## <a name="remarks"></a>Примечания

Каждая подпрограмма считывает один символ из **stdin** и увеличивает указатель связанного файла, чтобы он указывал на следующий символ. **GetChar** совпадает со значением [_fgetchar](fgetc-fgetwc.md), однако реализуется как функция и как макрос.

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

Консоль не поддерживается в приложениях универсальной платформы Windows (UWP). Стандартные дескрипторы потока, которые связаны с консоли, **stdin**, **stdout**, и **stderr**, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях UWP . Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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
