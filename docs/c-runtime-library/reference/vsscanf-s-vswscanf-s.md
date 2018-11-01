---
title: vsscanf_s, vswscanf_s
ms.date: 11/04/2016
apiname:
- vswscanf_s
- vsscanf_s
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
- vsscanf_s
- vswscanf_s
- _vstscanf_s
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
ms.openlocfilehash: 3106e3533f5bb65334f8a4f3d38f55d886faef4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477172"
---
# <a name="vsscanfs-vswscanfs"></a>vsscanf_s, vswscanf_s

Считывают форматированные данные из строки. Это версии функций [sscanf, vswscanf](vsscanf-vswscanf.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
int vsscanf_s(
   const char *buffer,
   const char *format,
   va_list argptr
);
int vswscanf_s(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Сохраненные данные

*format*<br/>
Строка управления форматом. Дополнительные сведения см. в разделе [Поля спецификации формата — функции scanf и wscanf](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*arglist*<br/>
Список аргументов переменных.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает количество полей, которые были успешно преобразованы и присвоены; возвращаемое значение не включает поля, которые были считаны, но не были присвоены. Возвращаемое значение 0 указывает, что поля не были назначены. Возвращает значение **EOF** при возникновении ошибки или достижения конца строки до первого преобразования.

Если *буфера* или *формат* — **NULL** вызывается указатель, обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают значение -1 и задайте **errno** для **EINVAL**.

Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**Vsscanf_s** функция считывает данные из *буфера* в расположения, указанные аргументами в *arglist* список аргументов. Аргументы в списке аргументов задают указатели на переменные, имеющие тип, соответствующий спецификатору типа в *формат*. В отличие от менее безопасной версии **vsscanf**, необходим параметр размера буфера, при использовании символов полей типа **c**, **C**, **s**, **S**, или наборов элементов управления строк, заключенных в **[]**. Размер буфера в символах должен указываться как дополнительный параметр сразу после каждого параметра буфера, которому он требуется.

Размер буфера включает завершающее значение NULL. Можно использовать поле спецификации ширины, чтобы гарантировать, что считываемый токен поместится в буфер. Если поле, указывающее ширину, не используется, а данные чтения токена слишком большие и не помещаются в буфер, в этот буфер ничего не записывается.

Дополнительные сведения см. в разделах [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) и [Символы поля типа scanf](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Параметр размера имеет тип **без знака**, а не **size_t**.

*Формат* аргумент определяет интерпретацию входных данных, поля и имеет те же форму и функцию как *формат* аргумент для **scanf_s** функции. Если производится копирование между перекрывающимися строками, поведение не определено.

**vswscanf_s** — это двухбайтовая версия **vsscanf_s**; аргументы для **vswscanf_s** представляют собой строки расширенных символов. **vsscanf_s** не обрабатывает многобайтовые шестнадцатеричные символы. **vswscanf_s** не обрабатывает шестнадцатеричном формате Юникода полной ширины и символы» зоны совместимости «. В противном случае **vswscanf_s** и **vsscanf_s** ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf_s**|**vsscanf_s**|**vsscanf_s**|**vswscanf_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**vsscanf_s**|\<stdio.h>|
|**vswscanf_s**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_vsscanf_s.c
// compile with: /W3
// This program uses vsscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

int call_vsscanf_s(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf_s(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));
    call_vsscanf_s(tokenstring, "%d", &i);
    call_vsscanf_s(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf, vswscanf](vsscanf-vswscanf.md)<br/>
