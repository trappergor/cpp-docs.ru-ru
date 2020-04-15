---
title: _makepath_s, _wmakepath_s
ms.date: 4/2/2020
api_name:
- _wmakepath_s
- _makepath_s
- _o__makepath_s
- _o__wmakepath_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 3a44651cb9ff8be806c45c6b6c5f41f810319a85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341606"
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

*Путь*<br/>
Буфер полного пути.

*sizeInWords*<br/>
Размер буфера в словах.

*размерInBytes*<br/>
Размер буфера в байтах.

*Диске*<br/>
Содержит букву (A, B и т. д.), соответствующую требуемому диску, с необязательным двоеточием после нее. **_makepath_s** автоматически вставляет толстую кишку в композитный путь, если она отсутствует. Если *диск* **NULL** или указывает на пустую строку, в строке композитного пути не отображается ни одна строка *диска.*

*dir*<br/>
Содержит путь каталогов, не включая обозначение диска или фактическое имя файла. Трейлинг слэш не является обязательным, и либо вперед\\слэш (/) или backslash ( ) или оба могут быть использованы в одном *аргументе dir.* Если конечная косая черта (/ или \\) не указана, она вставляется автоматически. Если *dir* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется путь каталога.

*Fname*<br/>
Содержит базовое имя файла без расширений. Если *fname* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется имя файла.

*Ext*<br/>
Содержит фактическое расширение имени файла с предшествующей точкой (.) или без нее. **_makepath_s** вставляет период автоматически, если он не отображается в *ext.* Если *ext* **null** или указывает на пустую строку, в строку композитного *пути* не вставляется расширение.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*Путь*|*размерinWords* / *размерInBytes*|Возвращает|Содержимое *пути*|
|------------|------------------------------------|------------|------------------------|
|**Null**|any|**EINVAL**|не изменено|
|any|<= 0|**EINVAL**|не изменено|

Если возникает любое из указанных выше условий ошибки, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функции возвращает **EINVAL**. **NULL** допускается для параметров *привода,* *fname,* и *ext*. Для получения информации о поведении, когда эти параметры являются нулевыми указателями или пустыми строками, см.

## <a name="remarks"></a>Remarks

Функция **_makepath_s** создает композитную строку пути из отдельных компонентов, сохраняя результат в *пути.* *Путь* может включать в себя письмо-диск, путь каталога, имя файла и расширение имени файла. **_wmakepath_s** является широкохарактерным вариантом **_makepath_s;** аргументы **в пользу _wmakepath_s** являются широкохарактерными строками. **_wmakepath_s** и **_makepath_s** ведут себя одинаково иначе.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

Аргумент *пути* должен указывать на пустой буфер, достаточно большой, чтобы удерживать полный путь. Композитный *путь* должен быть не больше **_MAX_PATH** констант, определяемый в Stdlib.h.

Если путь **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Кроме того, **errno** установлен на **EINVAL**. **Значения NULL** разрешены по всем другим параметрам.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

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

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
