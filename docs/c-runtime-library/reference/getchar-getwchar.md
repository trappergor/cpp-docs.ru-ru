---
title: getchar, getwchar
ms.date: 06/23/2020
api_name:
- getchar
- getwchar
- _o_getchar
- _o_getwchar
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c6a02f16c3ee3d3e3bc4f86026719a1bd2885416
ms.sourcegitcommit: 8645408c7929558b8162f781776d0908d790a41c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85334978"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Считывает символ из стандартного входного потока.

## <a name="syntax"></a>Синтаксис

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Эти функции ожидают ввода и не возвращают, пока не будут доступны входные данные.

Чтобы указать на ошибку чтения или конец файла, функция **GetChars** возвращает значение **EOF**, а **getwchar** возвращает **WEOF**. Для **GetChars**используйте **ferror** или **feof** для проверки ошибки или завершения файла.

## <a name="remarks"></a>Комментарии

Каждая подпрограммы считывает один символ из **stdin** и увеличивает связанный указатель файла, чтобы он указывал на следующий символ. Функция **GetChars** аналогична [_fgetchar](fgetc-fgetwc.md), но реализована в виде функции и макроса.

Эти функции также блокируют вызывающий поток и являются потокобезопасными. Описание неблокирующей версии см. в разделе [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**getchar**|**getchar**|**getwchar**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getchar**|\<stdio.h>|
|**getwchar**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях универсальная платформа Windows (UWP). Стандартные дескрипторы потока, связанные с консолью, **stdin**, **stdout**и **stderr**, должны быть перенаправляться до того, как функции времени выполнения C смогут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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
