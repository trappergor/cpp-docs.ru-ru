---
title: _searchenv_s, _wsearchenv_s
ms.date: 4/2/2020
api_name:
- _wsearchenv_s
- _searchenv_s
- _o__searchenv_s
- _o__wsearchenv_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3d526c546e1496b3b13b14a12c9025cbd0347cd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332399"
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

*Имени файла*<br/>
Имя искомого файла.

*варимя*<br/>
Искомая среда.

*Путь*<br/>
Буфер для хранения полного пути.

*numberOfElements*<br/>
Размер буфера *имени пути.*

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

Если *имя файла* является пустой строкой, значение возврата **ENOENT**.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Имени файла*|*варимя*|*Путь*|*numberOfElements*|Возвращаемое значение|Содержимое *имени пути*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|any|any|**Null**|any|**EINVAL**|Недоступно|
|**Null**|any|any|any|**EINVAL**|не изменено|
|any|any|any|<= 0|**EINVAL**|не изменено|

Если выполняется какое-либо из этих условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **EINVAL**.

## <a name="remarks"></a>Remarks

**В _searchenv_s** рутинный поиск целевого файла в указанном домене. Переменная *varname* может быть любой средой или определенной пользователем переменной, которая определяет список путей каталога, таких как **PATH,** **LIB**и **INCLUDE.** Поскольку **_searchenv_s** является чувствительным к случаю, *varname* должен соответствовать случаю переменной среды. Если *varname* не соответствует названию переменной среды, определенной в среде процесса, функция возвращаетнулась с нулем, а переменная *имени пути* остается неизменной.

Сначала процедура выполняет поиск файла в текущем рабочем каталоге. Если файл не найден, его поиск продолжается в каталогах, указанных в переменной среды. Если целевой файл находится в одном из этих каталогов, вновь созданный путь скопирован в *имя пути*. Если файл *имя файла* не найден, *имя пути* содержит пустую строку с нулевым завершением.

Буфер *имени пути* должен быть не менее **_MAX_PATH** символов, чтобы вместить всю длину построенного имени пути. В противном случае **_searchenv_s** может переполнить буфер *имени пути,* что приведет к неожиданному поведению.

**_wsearchenv_s** является широкохарактерным вариантом **_searchenv_s;** аргументы **в пользу _wsearchenv_s** являются широкохарактерными строками. **_wsearchenv_s** и **_searchenv_s** ведут себя одинаково иначе.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Управление каталогами](../../c-runtime-library/directory-control.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
