---
title: _splitpath_s, _wsplitpath_s
ms.date: 11/04/2016
apiname:
- _wsplitpath_s
- _splitpath_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: 87af8bac525844c06fdfc16d7d13a06eef4d61ab
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210449"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s

Разбивает имя пути на компоненты. Это версии функции [_splitpath, _wsplitpath](splitpath-wsplitpath.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>Параметры

*path*<br/>
Полный путь.

*Диск*<br/>
Буква, за которым следует двоеточие (**:**). Вы можете передать **NULL** для этого параметра, если буква диска не требуется.

*driveNumberOfElements*<br/>
Размер *диск* буфера в однобайтовых или расширенных символах. Если *диск* — **NULL**, это значение должно быть 0.

*dir*<br/>
Путь к каталогу, включая заключительную косую черту. Символ косой черты ( **/** ), обратной косой черты ( **\\** ), или оба могут использоваться. Вы можете передать **NULL** для этого параметра, если путь к каталогу не требуется.

*dirNumberOfElements*<br/>
Размер *dir* буфера в однобайтовых или расширенных символах. Если *dir* — **NULL**, это значение должно быть 0.

*fname*<br/>
Базовое имя файла (без расширения). Вы можете передать **NULL** для этого параметра, если имя файла не требуется.

*nameNumberOfElements*<br/>
Размер *fname* буфера в однобайтовых или расширенных символах. Если *fname* — **NULL**, это значение должно быть 0.

*Ext*<br/>
Расширение имени файла, включая ведущую точку (**.**). Вы можете передать **NULL** для этого параметра, если расширение имени файла не требуется.

*extNumberOfElements*<br/>
Размер *ext* буфера в однобайтовых или расширенных символах. Если *ext* — **NULL**, это значение должно быть 0.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Условия ошибок

|Условие|Возвращаемое значение|
|---------------|------------------|
|*путь* является **NULL**|**EINVAL**|
|*диск* — **NULL**, *driveNumberOfElements* имеет ненулевое значение|**EINVAL**|
|*диск* отличается от**NULL**, *driveNumberOfElements* равно нулю|**EINVAL**|
|*dir* — **NULL**, *dirNumberOfElements* имеет ненулевое значение|**EINVAL**|
|*dir* отличается от**NULL**, *dirNumberOfElements* равно нулю|**EINVAL**|
|*fname* — **NULL**, *nameNumberOfElements* имеет ненулевое значение|**EINVAL**|
|*fname* отличается от**NULL**, *nameNumberOfElements* равно нулю|**EINVAL**|
|*ext* — **NULL**, *extNumberOfElements* имеет ненулевое значение|**EINVAL**|
|*ext* отличается от**NULL**, *extNumberOfElements* равно нулю|**EINVAL**|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и вернуть **EINVAL**.

Если любой из буферов слишком мал для хранения результата, эти функции очищают все буферы, присваивают им пустые строки, устанавливают **errno** для **ERANGE**и возвращают **ERANGE**.

## <a name="remarks"></a>Примечания

**_Splitpath_s** функция разделяет путь на четыре компонента. **_splitpath_s** автоматически обрабатывает многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящий момент. **_wsplitpath_s** — это двухбайтовая версия **_splitpath_s**; аргументы для **_wsplitpath_s** представляют собой строки расширенных символов. В остальном эти функции ведут себя одинаково.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Каждый компонент полного пути сохраняется в отдельном буфере; константы манифеста **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**, и **_MAX_EXT** (определенных в STDLIB. H) укажите максимально допустимый размер каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

В приведенной ниже таблице перечислены значения констант манифеста.

|name|Значение|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Если полный путь не содержит некоторый компонент (например, имя файла), **_splitpath_s** присваивает соответствующему буферу пустую строку.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
