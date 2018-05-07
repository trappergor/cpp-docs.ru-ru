---
title: _mktemp_s, _wmktemp_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mktemp_s
- _wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs:
- C++
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0ed525f44150943496cddde57699035d8b62b6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s

Создает уникальное имя файла. Это версии функции [_mktemp, _wmktemp](mktemp-wmktemp.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*nametemplate, не равное*<br/>
Шаблон имени файла.

*sizeInChars*<br/>
Размер буфера в однобайтовых символов в **_mktemp_s**; расширенные символы в **_wmktemp_s**, включая завершающий символ null.

## <a name="return-value"></a>Возвращаемое значение

Обе этих функции возвращают нулевое значение в случае успешного выполнения; код ошибки — в случае сбоя.

### <a name="error-conditions"></a>Условия ошибок

|*nametemplate, не равное*|*sizeInChars*|Возвращаемое значение|Новое значение в *nametemplate, не равное*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**EINVAL**|**NULL**|
|Неверный формат (см. примечания в разделе правильный формат)|any|**EINVAL**|пустая строка|
|any|<= количество X|**EINVAL**|пустая строка|

Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функции возвращают **EINVAL**.

## <a name="remarks"></a>Примечания

**_Mktemp_s** функция создает уникальное имя файла, изменив *nametemplate, не равное* аргумента, чтобы после вызова, *nametemplate, не равное* указатель указывает на строку содержащий новое имя файла. **_mktemp_s** автоматически требуемым образом обрабатывает аргументы строки многобайтовых символов соответствующим образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящее время в системе во время выполнения. **_wmktemp_s** — это двухбайтовая версия **_mktemp_s**; аргумент **_wmktemp_s** представляет собой строку расширенных символов. **_wmktemp_s** и **_mktemp_s** ведут себя идентично, за исключением того, что **_wmktemp_s** не обрабатывает многобайтовые строки.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*Nametemplate, не равное* аргумент имеет форму **baseXXXXXX**, где *базового* является частью имени файла, указываемое и каждая X — это символ, предоставляемые **_mktemp_s**. Каждый символ заполнителя в *nametemplate, не равное* должно быть в верхнем регистре X. **_mktemp_s** сохраняет *базового* и заменяет первый конечные X буквы алфавита. **_mktemp_s** заменяет следующие конечные крестиками со значением 5 значный; это значение имеет уникальный номер, определяющий вызывающего процесса, или в многопоточных программах, вызывающий поток.

Каждого успешного вызова **_mktemp_s** изменяет *nametemplate, не равное*. В каждом последующем вызове из того же процесса или потока с таким же *nametemplate, не равное* аргумент, **_mktemp_s** проверяет имена файлов, совпадающих с именами, возвращенных **_mktemp_s** в предыдущих вызовах. Если файл не существует для данного имени **_mktemp_s** возвращает имя. Если файлы существуют для всех ранее результирующего имена, **_mktemp_s** создает новое имя, заменив буквы, он используется в возвращенный ранее имени на строчные буквы, по порядку, от «» до «z». Например если *базового* является:

> **fn**

и значение пяти цифр, предоставленное **_mktemp_s** 12345, возвращается имя:

> **fna12345**

Если это имя используется для создания файла FNA12345 и этот файл по-прежнему существует, возвращается следующее имя во время вызова из того же процесса или потока с таким же *базового* для *nametemplate, не равное* является:

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp_s** можно создавать не более 26 уникальных имен файлов для любой заданной комбинации *базового* и *nametemplate, не равное* значения. Таким образом, FNZ12345 — последний уникальное имя **_mktemp_s** можно создать для *базового* и *nametemplate, не равное* значения, используемые в этом примере.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
