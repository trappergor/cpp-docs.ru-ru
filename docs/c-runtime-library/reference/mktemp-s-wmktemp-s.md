---
title: _mktemp_s, _wmktemp_s
ms.date: 4/2/2020
api_name:
- _mktemp_s
- _wmktemp_s
- _o__mktemp_s
- _o__wmktemp_s
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
ms.openlocfilehash: 061c5647b2c5a5e79b017cf93989f62ad19cfc0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338757"
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

*nameTemplate*<br/>
Шаблон имени файла.

*размерInChars*<br/>
Размер буфера в однобайных символах **в _mktemp_s;** широкие символы в **_wmktemp_s,** включая нулевой терминатор.

## <a name="return-value"></a>Возвращаемое значение

Обе этих функции возвращают нулевое значение в случае успешного выполнения; код ошибки — в случае сбоя.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*nameTemplate*|*размерInChars*|Возвращаемое значение|Новое значение в *nameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**Null**|any|**EINVAL**|**Null**|
|Неправильный формат (см. раздел Замечания для правильного формата)|any|**EINVAL**|пустая строка|
|any|<= количество X|**EINVAL**|пустая строка|

Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функции возвращает **EINVAL**.

## <a name="remarks"></a>Remarks

Функция **_mktemp_s** создает уникальное имя файла, изменяя аргумент *nameTemplate,* так что после вызова указатель *nameTemplate* указывает на строку, содержащую новое имя файла. **_mktemp_s** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтовым кодом, который в настоящее время используется системой run-time. **_wmktemp_s** является широкохарактерным вариантом **_mktemp_s;** аргумент **_wmktemp_s** является широкохарактерным. **_wmktemp_s** и **_mktemp_s** ведут себя одинаково иначе, за исключением того, что **_wmktemp_s** не обрабатывает строки с мультибайт-символами.

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*Аргумент nameTemplate* имеет форму **baseXXXXXX**, где *база* является частью нового имени файла, которое вы поставляете, и каждый X является заполнителем для символа, поставляемого **_mktemp_s.** Каждый символ заполнителя в *nameTemplate* должен быть верхним X. **_mktemp_s** сохраняет *основание* и заменяет первый задний X с алфавитным характером. **_mktemp_s** заменяет следующие задние X с пятизначным значением; это значение является уникальным числом, определяющим процесс вызова, или в многопоточных программах, поток омрачить.

Каждый успешный вызов **для _mktemp_s** изменяет *nameTemplate.* В каждом последующем вызове из одного и того же процесса или потока с тем же аргументом *nameTemplate* **_mktemp_s** проверку имен файлов, которые соответствуют именам, возвращенным **_mktemp_s** в предыдущих вызовах. Если для данного имени не существует файла, **_mktemp_s** возвращает это имя. Если файлы существуют для всех ранее возвращенных имен, **_mktemp_s** создает новое имя, заменяя алфавитный символ, который он использовал в ранее возвращенном имени, следующей доступной буквой нижнего регистра, в порядке, от 'a' до 'z'. Например, если *база:*

> **Fn**

и пятизначное значение, поставляемое **_mktemp_s,** составляет 12345, возвращенное имя:

> **fna12345**

Если это имя используется для создания файла FNA12345 и этот файл все еще существует, следующее имя возвращается на вызов из того же процесса или поток с той же *базой* для *nameTemplate:*

> **fnb12345**

Если файл FNA12345 не существует, то опять возвращается следующее имя:

> **fna12345**

**_mktemp_s** может создать максимум 26 уникальных имен файлов для любой комбинации *значений базы* и *nameTemplate.* Таким образом, F-12345 является последним уникальным именем файла, **_mktemp_s** может создать для *базы* и *именШаблон* значения, используемые в этом примере.

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

### <a name="sample-output"></a>Пример выходных данных

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
