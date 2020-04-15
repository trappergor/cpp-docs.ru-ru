---
title: getchar, getwchar
ms.date: 4/2/2020
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4311b5b896a5a406ebe14f09e7bb525cb47951b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344617"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Считывает символ из стандартного входного потока.

## <a name="syntax"></a>Синтаксис

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Чтобы указать ошибку чтения или состояние конца файла, **getchar** возвращает **EOF**, и **getwchar** возвращает **WEOF**. Для **getchar,** используйте **ferror** или **feof** для того чтобы проверить для ошибки или для конца архива.

## <a name="remarks"></a>Remarks

Каждая рутина читает один символ из **stdin** и приращает связанный указатель файла, чтобы указать на следующий символ. **getchar** такой же, как [_fgetchar,](fgetc-fgetwc.md)но он реализуется как функция и как макрос.

Эти функции блокируют вызывающий поток, поэтому они потокобезопасны. Описание неблокирующей версии см. в разделе [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**гетчар**|**гетчар**|**getwchar**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**гетчар**|\<stdio.h>|
|**getwchar**|\<stdio.h> или \<wchar.h>|

Консоль не поддерживается в приложениях Universal Windows Platform (UWP). Стандартные ручьи потока, связанные с консолью, **stdin,** **stdout**и **stderr,** должны быть перенаправлены, прежде чем функции C run-time могут использовать их в приложениях UWP. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
