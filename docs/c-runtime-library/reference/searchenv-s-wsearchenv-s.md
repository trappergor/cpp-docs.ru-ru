---
title: _searchenv_s, _wsearchenv_s
ms.date: 11/04/2016
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
ms.openlocfilehash: 40c2d0c42a3d61f84db78015388eba19742af06e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505681"
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

*имя пути*<br/>
Буфер для хранения полного пути.

*numberOfElements*<br/>
Размер *pathname* буфера.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

Если *filename* является пустой строкой, возвращается значение **ENOENT**.

### <a name="error-conditions"></a>Условия ошибок

|*filename*|*varname*|*имя пути*|*numberOfElements*|Возвращаемое значение|Содержание *pathname*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|any|any|**NULL**|any|**EINVAL**|Н/Д|
|**NULL**|any|any|any|**EINVAL**|не изменено|
|any|any|any|<= 0|**EINVAL**|не изменено|

Если выполняется какое-либо из этих условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и вернуть **EINVAL**.

## <a name="remarks"></a>Примечания

**_Searchenv_s** поиск целевого файла в указанном домене. *Varname* переменная может быть любая переменная среды или определяемой пользователем переменной, содержащий список путей к каталогам, такие как **путь**, **LIB**, и **INCLUDE** . Так как **_searchenv_s** чувствителен к регистру, *varname* должен соответствовать регистру переменной среды. Если *varname* не совпадает с именем переменной среды, определенного в среде процесса, функция возвращает нуль и *pathname* переменной остается неизменным.

Сначала процедура выполняет поиск файла в текущем рабочем каталоге. Если файл не найден, его поиск продолжается в каталогах, указанных в переменной среды. Если целевой файл находится в одном из этих каталогов, созданный путь копируется в *pathname*. Если *filename* файл не найден, *pathname* содержит пустую строку с завершающим нулем.

*Pathname* буфера должен быть по крайней мере **_MAX_PATH** знаков, чтобы вместить полное имя созданного пути. В противном случае **_searchenv_s** может вызвать переполнение *pathname* буфера, приводит к непредвиденному поведению.

**_wsearchenv_s** — это двухбайтовая версия **_searchenv_s**; аргументы для **_wsearchenv_s** представляют собой строки расширенных символов. **_wsearchenv_s** и **_searchenv_s** идентично в противном случае.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

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
