---
title: _mktemp, _wmktemp
ms.date: 4/2/2020
api_name:
- _wmktemp
- _mktemp
- _o__mktemp
- _o__wmktemp
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
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
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
ms.openlocfilehash: 8affd20ca7826f0d383f749567c9625d61dacd48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338722"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp, _wmktemp

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

*nameTemplate*<br/>
Шаблон имени файла.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель на измененное имяШаблон. Функция возвращает **NULL,** если *nameTemplate* плохо сформирован или не более уникальные имена могут быть созданы из данного nameTemplate.

## <a name="remarks"></a>Remarks

Функция **_mktemp** создает уникальное имя файла, изменяя аргумент *nameTemplate.* **_mktemp** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтной страницей кода, которая в настоящее время используется системой run-time. **_wmktemp** является широкохарактерным вариантом **_mktemp;** аргументивация и значение возврата **_wmktemp** являются широкохарактерными строками. **_wmktemp** и **_mktemp** ведут себя одинаково иначе, за исключением того, что **_wmktemp** не обрабатывает строки с мультибайт-символами.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*Аргумент nameTemplate* имеет *базу*формы XXXXXX, где *основание* является частью нового имени файла, которое вы поставляете, и каждый X является заполнителем для персонажа, поставляемого **_mktemp.** Каждый символ заполнителя в *nameTemplate* должен быть верхним X. **_mktemp** сохраняет *основание* и заменяет первый задний X с алфавитным характером. **_mktemp** заменяет следующие задние X с пятизначным значением; это значение является уникальным числом, определяющим процесс вызова, или в многопоточных программах, поток омрачить.

Каждый успешный вызов **для _mktemp** изменяет *nameTemplate.* В каждом последующем вызове из одного и того же процесса или потока с тем же аргументом *nameTemplate* **_mktemp** проверку имен файлов, которые соответствуют именам, возвращенным **_mktemp** в предыдущих вызовах. Если для данного имени не существует файла, **_mktemp** возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, **_mktemp** создает новое имя, заменяя алфавитный символ, который он использовал в ранее возвращенном имени, следующей доступной буквой нижнего регистра, в порядке, от 'a' до 'z'. Например, если *база:*

> **Fn**

и пятизначное значение, поставляемое **_mktemp,** составляет 12345, возвращенное имя:

> **fna12345**

Если это имя используется для создания файла FNA12345 и этот файл все еще существует, следующее имя возвращается на вызов из того же процесса или поток с той же *базой* для *nameTemplate:*

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp** может создать максимум 26 уникальных имен файлов для любой комбинации *значений базы* и *nameTemplate.* Таким образом, F-12345 является последним уникальным именем **файла, _mktemp** может создать для *базы* и *именШаблон* значения, используемые в этом примере.

На отказе, **errno** установлен. Если *nameTemplate* имеет недействительный формат (например, менее 6 X), **errno** устанавливается в **EINVAL.** Если **_mktemp** не может создать уникальное имя, потому что все 26 возможных имен файлов уже существуют, **_mktemp** устанавливает nameTemplate к пустой строке и возвращает **EEXIST**.

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
