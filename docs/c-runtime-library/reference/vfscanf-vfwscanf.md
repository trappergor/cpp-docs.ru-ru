---
title: vfscanf, vfwscanf | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- vfwscanf
- vfscanf
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
apitype: DLLExport
f1_keywords:
- vfwscanf
- _vftscanf
- vfscanf
dev_langs:
- C++
ms.assetid: c06450ef-03f1-4d24-a8ac-d2dd98847918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7b7194aa5b7c60b03e3701567ffdb236f32f0b3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="vfscanf-vfwscanf"></a>vfscanf, vfwscanf

Считывают форматированные данные из потока. Существуют более безопасные версии этих функций; см. раздел [vfscanf_s, vfwscanf_s](vfscanf-s-vfwscanf-s.md).

## <a name="syntax"></a>Синтаксис

```C
int vfscanf(
   FILE *stream,
   const char *format,
   va_list argptr
);
int vfwscanf(
   FILE *stream,
   const wchar_t *format,
   va_list argptr
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Указатель на структуру **FILE**.

*format*<br/>
Строка управления форматом.

*arglist*<br/>
Список аргументов переменных.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает количество полей, которые были успешно преобразованы и присвоены; возвращаемое значение не включает поля, которые считываются, но не присваиваются. Возвращаемое значение 0 указывает, что поля не были назначены. Если происходит ошибка или если достигнут конец потока файла до первого преобразования, возвращаемым значением является **EOF** для **vfscanf** и **vfwscanf**.

Эти функции проверяют свои параметры. Если *поток* или *формат* является пустым указателем, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EOF** и задайте **errno** для **EINVAL**.

## <a name="remarks"></a>Примечания

**Vfscanf** функция считывает данные из текущей позиции *поток* в расположения, заданные *arglist* список аргументов. Каждый аргумент в списке должен быть указателем на переменную типа, соответствующий спецификатору типа в *формат*. *формат* определяет интерпретацию входных данных поля и имеет те же форму и функциональные возможности, что *формат* аргумент для **scanf**; в разделе [scanf](scanf-scanf-l-wscanf-wscanf-l.md) для Описание *формат*.

**vfwscanf** — это двухбайтовая версия **vfscanf**; формат аргумент **vfwscanf** представляет собой строку расширенных символов. Эти функции ведут себя одинаково, если поток открыт в режиме ANSI. **vfscanf** не поддерживает входные данные из потока ЮНИКОДА.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vftscanf**|**vfscanf**|**vfscanf**|**vfwscanf**|

Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**vfscanf**|\<stdio.h>|
|**vfwscanf**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_vfscanf.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses vfscanf to
// read the various data back from the file.

#include <stdio.h>
#include <stdarg.h>

FILE *stream;

int call_vfscanf(FILE * istream, char * format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vfscanf(istream, format, arglist);
    va_end(arglist);
    return result;
}

int main(void)
{
    long l;
    float fp;
    char s[81];
    char c;

    if (fopen_s(&stream, "vfscanf.out", "w+") != 0)
    {
        printf("The file vfscanf.out was not opened\n");
    }
    else
    {
        fprintf(stream, "%s %ld %f%c", "a-string",
            65000, 3.14159, 'x');
        // Security caution!
        // Beware loading data from a file without confirming its size,
        // as it may lead to a buffer overrun situation.

        // Set pointer to beginning of file:
        fseek(stream, 0L, SEEK_SET);

        // Read data back from file:
        call_vfscanf(stream, "%s %ld %f%c", s, &l, &fp, &c);

        // Output data read:
        printf("%s\n", s);
        printf("%ld\n", l);
        printf("%f\n", fp);
        printf("%c\n", c);

        fclose(stream);
    }
}

```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
[vfscanf_s, vfwscanf_s](vfscanf-s-vfwscanf-s.md)<br/>
