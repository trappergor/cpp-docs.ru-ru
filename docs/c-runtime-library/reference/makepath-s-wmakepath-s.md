---
title: _makepath_s, _wmakepath_s
ms.date: 11/04/2016
api_name:
- _wmakepath_s
- _makepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 7bd85734e71120a214d652048c02c176728474b2
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624359"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s, _wmakepath_s

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

*сизеинвордс*<br/>
Размер буфера в словах.

*сизеинбитес*<br/>
Размер буфера в байтах.

*диск*<br/>
Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. **_makepath_s** вставляет двоеточие автоматически в составной путь, если он отсутствует. Если параметр *Drive* имеет **значение NULL** или указывает на пустую строку, буква диска не отображается в строке составного *пути* .

*команды*<br/>
Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Замыкающая косая черта является необязательной, и в одном аргументе *dir* может использоваться косая черта (/) или обратная косая черта (\\). Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если параметр *dir* имеет **значение NULL** или указывает на пустую строку, путь к каталогу не вставляется в строку составного *пути* .

*fname*<br/>
Содержит базовое имя файла без расширений. Если параметр *fname* имеет **значение NULL** или указывает на пустую строку, имя файла не вставляется в строку составного *пути* .

*WLAN*<br/>
Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. **_makepath_s** вставляет период автоматически, если он не появился в *ext*. Если *ext* имеет **значение NULL** или указывает на пустую строку, расширение не вставляется в строку составного *пути* .

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Условия ошибок

|*path*|*сизеинвордс* / *сизеинбитес*|Назад|Содержимое *пути*|
|------------|------------------------------------|------------|------------------------|
|**NULL**|Любое действие|**EINVAL**|не изменено|
|Любое действие|<= 0|**EINVAL**|не изменено|

Если возникает любое из указанных выше условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, функция** возвращает значение **еинвал** , а функции возвращают **еинвал**. **Значение NULL** допустимо для параметров *Drive*, *fname*и *ext*. Сведения о поведении, когда эти параметры являются указателями null или пустыми строками, см. в разделе "Примечания".

## <a name="remarks"></a>Заметки

Функция **_makepath_s** создает строку составного пути из отдельных компонентов, сохраняя результат в *path*. *Путь* может содержать букву диска, путь к каталогу, имя файла и расширение имени файла. **_wmakepath_s** — это версия **_makepath_s**для расширенных символов; аргументы для **_wmakepath_s** являются строками расширенных символов. в противном случае **_wmakepath_s** и **_makepath_s** ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

Аргумент *path* должен указывать на пустой буфер, достаточно большой для хранения полного пути. Составной *путь* должен быть не больше константы **_MAX_PATH** , определенной в STDLIB. h.

Если параметр path имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того, для параметра « **еинвал**» задано значение **«нет»** . Значения **null** допускаются для всех остальных параметров.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Версии отладочной библиотеки этих функций сначала заполняют буфер 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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
