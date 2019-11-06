---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
api_name:
- _mktemp_s
- _wmktemp_s
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
ms.openlocfilehash: 464f0dfbdb0b84e1fd29ec650e53f5c2543c4403
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624214"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s, _wmktemp_s

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

*наметемплате*<br/>
Шаблон имени файла.

*сизеинчарс*<br/>
Размер буфера в однобайтовых символах в **_mktemp_s**; широкие символы в **_wmktemp_s**, включая знак завершения null.

## <a name="return-value"></a>Возвращаемое значение

Обе этих функции возвращают нулевое значение в случае успешного выполнения; код ошибки — в случае сбоя.

### <a name="error-conditions"></a>Условия ошибок

|*наметемплате*|*сизеинчарс*|Возвращаемое значение|Новое значение в *наметемплате*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|Любое действие|**EINVAL**|**NULL**|
|Неправильный формат (см. раздел "Примечания" для правильного формата)|Любое действие|**EINVAL**|пустая строка|
|Любое действие|<= количество X|**EINVAL**|пустая строка|

Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, функция** возвращает значение **еинвал** , а функции возвращают **еинвал**.

## <a name="remarks"></a>Заметки

Функция **_mktemp_s** создает уникальное имя файла, изменяя аргумент *наметемплате* , поэтому после вызова указатель *наметемплате* указывает на строку, содержащую новое имя файла. **_mktemp_s** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с многобайтовой кодовой страницей, используемой в настоящее время системой выполнения. **_wmktemp_s** — это версия **_mktemp_s**для расширенных символов; Аргумент **_wmktemp_s** является строкой расширенных символов. поведение **_wmktemp_s** и **_mktemp_s** идентично в других случаях, за исключением того, что **_wmktemp_s** не обрабатывает строки многобайтовых символов.

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

Аргумент *наметемплате* имеет форму **басекскскскскскс**, где *base* — это часть нового имени файла, которую вы указали, а каждый X является заполнителем для символа, предоставленного **_mktemp_s**. Каждый символ заполнителя в *наметемплате* должен быть прописной буквой X. **_mktemp_s** сохраняет *основу* и заменяет первый замыкающий символ буквой. **_mktemp_s** заменяет следующий символ X на значение из пяти цифр; Это значение представляет собой уникальный номер, идентифицирующий вызывающий процесс или в многопоточных программах, вызывающий поток.

Каждый успешный вызов **_mktemp_s** изменяет *наметемплате*. В каждом последующем вызове из того же процесса или потока с одним и тем же аргументом *наметемплате* **_mktemp_s** проверяет наличие имен файлов, соответствующих именам, возвращенным **_mktemp_s** в предыдущих вызовах. Если для данного имени файл не существует, **_mktemp_s** возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, **_mktemp_s** создает новое имя, заменяя букву, которая использовалась в ранее возвращенном имени, на следующую доступную строчную букву в порядке от "a" до "z". Например, если *base* имеет значение:

> **FN**

и пять-значным значением, предоставленным функцией **_mktemp_s** , является 12345, первым возвращенным именем будет:

> **fna12345**

Если это имя используется для создания файла FNA12345, а этот файл по-прежнему существует, то следующее имя, возвращаемое при вызове из того же процесса или потока с той же *базой* для *наметемплате* , имеет следующий результат:

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp_s** может создавать не более 26 уникальных имен файлов для любой заданной комбинации *базовых* и *наметемплате* значений. Таким образом, FNZ12345 — это Последнее уникальное имя файла **_mktemp_s** , которое может быть создано для значений *base* и *наметемплате* , используемых в этом примере.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
