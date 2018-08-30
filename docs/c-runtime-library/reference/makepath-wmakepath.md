---
title: _makepath, _wmakepath | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _makepath
- _wmakepath
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
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20985ce09d301002e6db3164cc3e99f36b03717b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204908"
---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath

Создают путь из компонентов. Существуют более безопасные версии этих функций; см. раздел [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="syntax"></a>Синтаксис

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>Параметры

*путь* буфер полного пути.

*диск* содержит буквы (A, B и т. д.), соответствующее требуемому диску и необязательным двоеточием. **_makepath** вставляет двоеточие автоматически в составной путь, если он отсутствует. Если *диск* — **NULL** или указывает на пустую строку, буква диска не отображается в составную *путь* строка.

*dir* содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Конечная косая черта является необязательным и косой черты (/) или обратную косую черту (\\) или оба могут использоваться в одном *dir* аргумент. Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если *dir* — **NULL** или указывает на пустую строку, путь каталога не вставляется в составную *путь* строка.

*fname* содержит базовое имя файла без расширений. Если *fname* — **NULL** или указывает на пустую строку, имя файла не вставляется в составную *путь* строка.

*ext* содержит фактическое расширение, независимо от точки (..) в начале. **_makepath** вставляет точку автоматически, если он не отображается в *ext*. Если *ext* — **NULL** или указывает на пустую строку, расширение не вставляется в составную *путь* строка.

## <a name="remarks"></a>Примечания

**_Makepath** функция создает строку составного пути из отдельных компонентов, сохраняя результат в *путь*. *Путь* может включать букву диска, путь к каталогу, имя файла и расширение имени файла. **_wmakepath** — это двухбайтовая версия **_makepath**; аргументы для **_wmakepath** представляют собой строки расширенных символов. **_wmakepath** и **_makepath** идентично в противном случае.

**Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Чтобы избежать переполнения буфера, заканчивающаяся нулем строка не должна превышать размер *путь* буфера. **_makepath** убедитесь, что длина строки составного пути не превышает **_MAX_PATH**. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*Путь* аргумент должен указывать на пустой буфер недостаточно велик для хранения полного пути. Составной *путь* должно быть не больше, чем **_MAX_PATH** константа, определенная в файле Stdlib.h.

Если путь **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Кроме того **errno** присваивается **EINVAL**. **NULL** для всех остальных параметров допускаются значения.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
