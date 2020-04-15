---
title: _makepath, _wmakepath
ms.date: 4/2/2020
api_name:
- _makepath
- _wmakepath
- _o__makepath
- _o__wmakepath
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: b92e056816183b4bbb07edb3efec4415655d655e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341584"
---
# <a name="_makepath-_wmakepath"></a>_makepath, _wmakepath

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

*Путь*<br/>
Буфер полного пути.

*Диске*<br/>
Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. **_makepath** автоматически вставляет толстую кишку в композитный путь, если она отсутствует. Если *диск* **NULL** или указывает на пустую строку, в строке композитного пути не отображается ни одна строка *диска.*

*dir*<br/>
Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Трейлинг слэш не является обязательным, и либо вперед\\слэш (/) или backslash ( ) или оба могут быть использованы в одном *аргументе dir.* Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если *dir* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется путь каталога.

*Fname*<br/>
Содержит базовое имя файла без расширений. Если *fname* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется имя файла.

*Ext*<br/>
Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. **_makepath** вставляет период автоматически, если он не отображается в *ext.* Если *ext* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется расширение.

## <a name="remarks"></a>Remarks

Функция **_makepath** создает композитную строку пути из отдельных компонентов, сохраняя результат в *пути.* *Путь* может включать в себя письмо-диск, траекторию каталога, имя файла и расширение имени файлов. **_wmakepath** является широкохарактерным вариантом **_makepath;** аргументы **в пользу _wmakepath** являются широкохарактерными строками. **_wmakepath** и **_makepath** ведут себя одинаково иначе.

**Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Чтобы избежать перезапуска буфера, нулевая строка не должна превышать размер буфера *пути.* **_makepath** не гарантирует, что длина строки композитного пути не превышает **_MAX_PATH.** Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

Аргумент *пути* должен указывать на пустой буфер, достаточно большой, чтобы удерживать полный путь. Композитный *путь* должен быть не больше **_MAX_PATH** констант, определяемый в Stdlib.h.

Если путь **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Кроме того, **errno** установлен на **EINVAL**. **Значения NULL** разрешены по всем другим параметрам.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
