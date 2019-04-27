---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
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
ms.openlocfilehash: fef10f2cfbcc0332741d560a41a782b70ed14798
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156542"
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
Размер буфера в однобайтовых символов в **_mktemp_s**, в расширенных символов в **_wmktemp_s**, включая завершающий символ null.

## <a name="return-value"></a>Возвращаемое значение

Обе этих функции возвращают нулевое значение в случае успешного выполнения; код ошибки — в случае сбоя.

### <a name="error-conditions"></a>Условия ошибок

|*nametemplate, не равное*|*sizeInChars*|Возвращаемое значение|Новое значение в *nametemplate, не равное*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|any|**EINVAL**|**NULL**|
|Неверный формат (см. в разделе "Примечания" раздела о правильном формате)|any|**EINVAL**|пустая строка|
|any|<= количество X|**EINVAL**|пустая строка|

Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функции возвращают **EINVAL**.

## <a name="remarks"></a>Примечания

**_Mktemp_s** функция создает уникальное имя файла, изменяя *nametemplate, не равное* аргумент, таким образом, чтобы после вызова *nametemplate, не равное* указатель указывает на строку содержащая новое имя файла. **_mktemp_s** автоматически обрабатывает многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящий момент в системе во время выполнения. **_wmktemp_s** — это двухбайтовая версия **_mktemp_s**; аргумент **_wmktemp_s** — строка расширенных символов. **_wmktemp_s** и **_mktemp_s** ведут себя идентично, за исключением случаев, **_wmktemp_s** не обрабатывает многобайтовые строки.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*Nametemplate, не равное* аргумент имеет форму **baseXXXXXX**, где *базового* является частью новое имя файла, который вы указали, а X — это заполнитель для символа, указанного в **_mktemp_s**. Каждый символ заполнителя в *nametemplate, не равное* должно быть в верхнем регистре X. **_mktemp_s** сохраняет *базового* и заменяет первый конечный символ X с алфавитного символа. **_mktemp_s** заменяет следующие конечные символов x со значением 5 значный; это значение является уникальным номером, определяющим вызывающий процесс, а в многопоточных программах, вызывающий поток.

Каждого успешного вызова **_mktemp_s** изменяет *nametemplate, не равное*. В каждом последующем вызове из одного процесса или потока с таким же *nametemplate, не равное* аргумент, **_mktemp_s** проверяет имена файлов, совпадающих с именами, возвращенный **_mktemp_s** в предыдущих вызовах. Если файл не существует для заданного имени, **_mktemp_s** возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, **_mktemp_s** создает новое имя, заменяя букву, он используется в ранее возвращенном имени, с помощью следующей доступной строчной буквой по порядку от «» до «z». Например если *базового* является:

> **fn**

и 5 значный значение, предоставленное **_mktemp_s** — 12345, возвращается имя первого:

> **файл fna12345**

Если это имя используется для создания файла FNA12345 и этот файл по-прежнему существует, следующее имя, возвращаемое из одного процесса или потока с таким же *базового* для *nametemplate, не равное* является:

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **файл fna12345**

**_mktemp_s** можно создать до 26 уникальных имен файлов для любого заданного сочетания *базового* и *nametemplate, не равное* значения. Таким образом, FNZ12345 является последним уникальным именем файла **_mktemp_s** можно создать для *базового* и *nametemplate, не равное* значения, используемые в этом примере.

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
