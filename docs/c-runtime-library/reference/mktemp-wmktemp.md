---
title: _mktemp, _wmktemp | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wmktemp
- _mktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c270623c0ea81294295e949a90de2a770db0b16
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp

Создает уникальное имя файла. Существуют более безопасные версии этих функций; см. раздел [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

## <a name="syntax"></a>Синтаксис

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*nametemplate, не равное*<br/>
Шаблон имени файла.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на измененную nametemplate, не равное. Функция возвращает **NULL** Если *nametemplate, не равное* неправильно сформирован или больше уникальные имена, которые могут быть созданы из данного nametemplate, не равное.

## <a name="remarks"></a>Примечания

**_Mktemp** функция создает уникальное имя файла, изменив *nametemplate, не равное* аргумент. **_mktemp** автоматически требуемым образом обрабатывает аргументы строки многобайтовых символов соответствующим образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящее время в системе во время выполнения. **_wmktemp** — это двухбайтовая версия **_mktemp**; аргумент и возвращаемое значение **_wmktemp** представляют собой строки расширенных символов. **_wmktemp** и **_mktemp** ведут себя идентично, за исключением того, что **_wmktemp** не обрабатывает многобайтовые строки.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*Nametemplate, не равное* аргумент имеет форму *базового ** XXXXXX*, где *базового* является частью имени файла, указываемое и каждая X — это символ, предоставляемые **_mktemp**. Каждый символ заполнителя в *nametemplate, не равное* должно быть в верхнем регистре X. **_mktemp** сохраняет *базового* и заменяет первый конечные X буквы алфавита. **_mktemp** заменяет следующие конечные крестиками со значением 5 значный; это значение имеет уникальный номер, определяющий вызывающего процесса, или в многопоточных программах, вызывающий поток.

Каждого успешного вызова **_mktemp** изменяет *nametemplate, не равное*. В каждом последующем вызове из того же процесса или потока с таким же *nametemplate, не равное* аргумент, **_mktemp** проверяет имена файлов, совпадающих с именами, возвращенных **_mktemp** в предыдущих вызовов. Если файл не существует для данного имени **_mktemp** возвращает имя. Если файлы существуют для всех ранее результирующего имена, **_mktemp** создает новое имя, заменив буквы, он используется в возвращенный ранее имени на строчные буквы, по порядку, от «» до «z». Например если *базового* является:

> **fn**

и значение пяти цифр, предоставленное **_mktemp** 12345, возвращается имя:

> **fna12345**

Если это имя используется для создания файла FNA12345 и этот файл по-прежнему существует, возвращается следующее имя во время вызова из того же процесса или потока с таким же *базового* для *nametemplate, не равное* является:

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp** можно создавать не более 26 уникальных имен файлов для любой заданной комбинации *базового* и *nametemplate, не равное* значения. Таким образом, FNZ12345 — последний уникальное имя **_mktemp** можно создать для *базового* и *nametemplate, не равное* значения, используемые в этом примере.

В случае сбоя **errno** имеет значение. Если *nametemplate, не равное* имеет недопустимый формат (например, менее 6 крестиками), **errno** равно **EINVAL**. Если **_mktemp** не удалось создать уникальное имя, поскольку 26 Возможные имена уже существуют, **_mktemp** задает nametemplate, не равное пустую строку и возвращает **EEXIST**.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
