---
title: _searchenv_s, _wsearchenv_s
ms.date: 11/04/2016
api_name:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: 606215fb7a2cce7929b29e2035f8e03556ca25e0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948790"
---
# <a name="_searchenv_s-_wsearchenv_s"></a>_searchenv_s, _wsearchenv_s

Ищет файл, используя пути в среде. Это версии функций [_searchenv, _wsearchenv](searchenv-wsearchenv.md) с повышенной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя искомого файла.

*varname*<br/>
Искомая среда.

*контура*<br/>
Буфер для хранения полного пути.

*numberOfElements*<br/>
Размер буфера *PathName* .

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

Если *filename* является пустой строкой, возвращается значение **еноент**.

### <a name="error-conditions"></a>Условия ошибок

|*filename*|*varname*|*контура*|*numberOfElements*|Возвращаемое значение|Содержимое *пути*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|Любое действие|Любое действие|**NULL**|Любое действие|**EINVAL**|Н/Д|
|**NULL**|Любое действие|Любое действие|Любое действие|**EINVAL**|не изменено|
|Любое действие|Любое действие|Любое действие|<= 0|**EINVAL**|не изменено|

Если выполняется какое-либо из этих условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции **устанавливают** значение **еинвал** и возвращают **еинвал**.

## <a name="remarks"></a>Примечания

Подпрограммы **_searchenv_s** выполняет поиск целевого файла в указанном домене. Переменная *имя_переменной* может быть любой средой или определяемой пользователем переменной, указывающей список путей к каталогам, например **path**, **lib**и **include**. Так как **_searchenv_s** учитывает регистр, переменная *имя_переменной* должна соответствовать регистру переменной среды. Если *имя_переменной* не совпадает с именем переменной среды, определенной в среде процесса, функция возвращает ноль, а переменная *PathName* не изменяется.

Сначала процедура выполняет поиск файла в текущем рабочем каталоге. Если файл не найден, его поиск продолжается в каталогах, указанных в переменной среды. Если целевой файл находится в одном из этих каталогов, созданный путь копируется в *путь*. Если файл *имени* файла не найден, то *PathName* содержит пустую строку, завершающуюся нулем.

Буфер *PathName* должен иметь длину не менее **_MAX_PATH** символов, чтобы соответствовать полной длине сформированного пути. В противном случае **_searchenv_s** может привести к переполнению буфера *PathName* , что привело к непредвиденному поведению.

**_wsearchenv_s** — это версия **_searchenv_s**для расширенных символов; аргументы для **_wsearchenv_s** являются строками расширенных символов. в противном случае **_wsearchenv_s** и **_searchenv_s** ведут себя одинаково.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>См. также

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
