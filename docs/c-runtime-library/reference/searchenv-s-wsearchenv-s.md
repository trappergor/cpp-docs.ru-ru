---
title: _searchenv_s, _wsearchenv_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsearchenv_s
- _searchenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14dee908cdf1cc0d564047035a72f501df130b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410919"
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s, _wsearchenv_s

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

*PathName*<br/>
Буфер для хранения полного пути.

*numberOfElements*<br/>
Размер *pathname* буфера.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

Если *filename* является пустой строкой, возвращается значение **ENOENT**.

### <a name="error-conditions"></a>Условия ошибок

|*filename*|*varname*|*PathName*|*numberOfElements*|Возвращаемое значение|Содержимое *pathname*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|any|any|**NULL**|any|**EINVAL**|Н/Д|
|**NULL**|any|any|any|**EINVAL**|не изменено|
|any|any|any|<= 0|**EINVAL**|не изменено|

Если выполняется какое-либо из этих условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **EINVAL**.

## <a name="remarks"></a>Примечания

**_Searchenv_s** сопоставление ищет целевой файл в указанном домене. *Varname* переменной может быть любым среды или определяемой пользователем переменной, указывающий список путей к каталогам, таких как **путь**, **LIB**, и **INCLUDE** . Поскольку **_searchenv_s** учитывается регистр, *varname* должен соответствовать регистру переменной среды. Если *varname* не соответствует имя переменной среды, определенные в среде процесса, функция возвращает ноль и *pathname* переменной не изменяется.

Сначала процедура выполняет поиск файла в текущем рабочем каталоге. Если файл не найден, его поиск продолжается в каталогах, указанных в переменной среды. Если целевой файл содержится в одном из этих каталогов, созданный путь копируется в *pathname*. Если *filename* файл не найден, *pathname* содержит пустую строку, завершающуюся значением null.

*Pathname* буфера должен быть по крайней мере **_MAX_PATH** знаков, чтобы вместить полное имя созданного пути. В противном случае **_searchenv_s** может вызвать переполнение *pathname* буфера, что приводит к непредвиденному поведению.

**_wsearchenv_s** — это двухбайтовая версия **_searchenv_s**; аргументы для **_wsearchenv_s** представляют собой строки расширенных символов. **_wsearchenv_s** и **_searchenv_s** ведут себя идентично.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
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
