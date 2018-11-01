---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
apiname:
- _wmakepath_s
- _makepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 6914299dd7ede97c9004dcc95e01b1a35188f5c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471920"
---
# <a name="makepaths-wmakepaths"></a>_makepath_s, _wmakepath_s

Создает путь из компонентов. Это версии функции [_makepath, _wmakepath](makepath-wmakepath.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствование безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>Параметры

*path*<br/>
Буфер полного пути.

*sizeInWords*<br/>
Размер буфера в словах.

*sizeInBytes*<br/>
Размер буфера в байтах.

*Диск*<br/>
Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. **_makepath_s** вставляет двоеточие автоматически в составной путь, если он отсутствует. Если *диск* — **NULL** или указывает на пустую строку, буква диска не отображается в составную *путь* строка.

*dir*<br/>
Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Конечная косая черта является необязательным и косой черты (/) или обратную косую черту (\\) или оба могут использоваться в одном *dir* аргумент. Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если *dir* — **NULL** или указывает на пустую строку, путь каталога не вставляется в составную *путь* строка.

*fname*<br/>
Содержит базовое имя файла без расширений. Если *fname* — **NULL** или указывает на пустую строку, имя файла не вставляется в составную *путь* строка.

*Ext*<br/>
Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. **_makepath_s** вставляет точку автоматически, если он не отображается в *ext*. Если *ext* — **NULL** или указывает на пустую строку, расширение не вставляется в составную *путь* строка.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Условия ошибок

|*path*|*sizeInWords* / *sizeInBytes*|Назад|Содержание *путь*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|any|**EINVAL**|не изменено|
|any|<= 0|**EINVAL**|не изменено|

Если возникает любое из указанных выше условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функции возвращают **EINVAL**. **NULL** допускается для параметров *диск*, *fname*, и *ext*. Дополнительные сведения о поведении в случае, когда эти параметры являются указателями NULL или пустыми строками, см. в разделе примечаний.

## <a name="remarks"></a>Примечания

**_Makepath_s** функция создает строку составного пути из отдельных компонентов, сохраняя результат в *путь*. *Путь* может включать букву диска, путь к каталогу, имя файла и расширение имени файла. **_wmakepath_s** — это двухбайтовая версия **_makepath_s**; аргументы для **_wmakepath_s** представляют собой строки расширенных символов. **_wmakepath_s** и **_makepath_s** идентично в противном случае.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*Путь* аргумент должен указывать на пустой буфер недостаточно велик для хранения полного пути. Составной *путь* должно быть не больше, чем **_MAX_PATH** константа, определенная в файле Stdlib.h.

Если путь **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того **errno** присваивается **EINVAL**. **NULL** для всех остальных параметров допускаются значения.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
