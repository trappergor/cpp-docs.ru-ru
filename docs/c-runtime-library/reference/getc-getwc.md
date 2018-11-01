---
title: getc, getwc
ms.date: 11/04/2016
apiname:
- getwc
- getc
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
- _gettc
- getwc
- _gettchar
- getc
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
ms.openlocfilehash: bbaee79eac6802959a11f7f1ba30eaf590ecf2f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664871"
---
# <a name="getc-getwc"></a>getc, getwc

Считывает символ из потока.

## <a name="syntax"></a>Синтаксис

```C
int getc(
   FILE *stream
);
wint_t getwc(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Входной поток.

## <a name="return-value"></a>Возвращаемое значение

Возвращает считанный символ. Чтобы указать на ошибку чтения или конец файла, **getc** возвращает **EOF**, и **getwc** возвращает **WEOF**. Для **getc**, использовать **ferror** или **feof** для проверки наличия ошибки или достижение конца файла. Если *поток* — **NULL**, **getc** и **getwc** вызывают обработчик недопустимого параметра, как описано в [параметр Проверка](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EOF** (или **WEOF** для **getwc**) и задайте **errno** для  **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Каждая подпрограмма считывает один символ из файла в текущей позиции и увеличивает связанный указатель файла (если он определен), чтобы он указывал на следующий символ. Файл связан с *поток*.

Эти функции блокируют вызывающий поток, поэтому они потокобезопасны. Описание неблокирующей версии см. в разделе [_getc_nolock, _getwc_nolock](getc-nolock-getwc-nolock.md).

Ниже приводятся примечания для конкретных подпрограмм.

|Подпрограмма|Примечания|
|-------------|-------------|
|**getc**|Совпадение с кодом **fgetc**, но реализованный как функция и как макрос.|
|**getwc**|Двухбайтовая версия **getc**. Считывает Многобайтовый или расширенный символ согласно ли *поток* открыт в текстовом или двоичном режиме.|

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getc.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc.txt".

    fopen_s(&fp, "crt_getc.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc.txt.\n");
       exit(1);
    }

    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);

    fclose(fp);
}
```

### <a name="input-crtgetctxt"></a>Входные данные: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>Вывод

```Output
Input was: Line one.
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
