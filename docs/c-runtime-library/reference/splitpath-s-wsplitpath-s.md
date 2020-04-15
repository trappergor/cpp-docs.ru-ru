---
title: _splitpath_s, _wsplitpath_s
ms.date: 4/2/2020
api_name:
- _wsplitpath_s
- _splitpath_s
- _o__splitpath_s
- _o__wsplitpath_s
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
ms.openlocfilehash: 364544a9423668494747405e801d59b73de4e6c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355617"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

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

*Путь*<br/>
Полный путь.

*Диске*<br/>
Привод письмо, а затем толстой кишки (**:**). Вы можете пройти **NULL** для этого параметра, если вам не нужно письмо диска.

*driveNumberOfelements*<br/>
Размер буфера *диска* в однобайных или широких символах. Если *диск* **NULL,** это значение должно быть 0.

*dir*<br/>
Путь к каталогу, включая заключительную косую черту. Передние **/** слэши ( **\\** ), backslashes ( ), или оба могут быть использованы. Вы можете пройти **NULL** для этого параметра, если вам не нужен путь каталога.

*dirNumberofElements*<br/>
Размер буфера *dir* в однобайных или широких символах. Если *dir* dir **null,** это значение должно быть 0.

*Fname*<br/>
Базовое имя файла (без расширения). Вы можете пройти **NULL** для этого параметра, если вам не нужно имя файла.

*nameNumberOfElements*<br/>
Размер буфера *fname* в однобайных или широких символах. Если *fname* **NULL,** это значение должно быть 0.

*Ext*<br/>
Продление Filename, включая опережая **(. ).** Вы можете пройти **NULL** для этого параметра, если вам не нужно расширение имя файла.

*extNumberOfElements*<br/>
Размер *буфера ext* в однобайных или широких символах. Если *ext* **null,** это значение должно быть 0.

## <a name="return-value"></a>Возвращаемое значение

Возвращает нуль в случае успеха или код ошибки в случае неудачи.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|Условие|Возвращаемое значение|
|---------------|------------------|
|*путь* **NULL**|**EINVAL**|
|*диск* **NULL**, *driveNumberOfElements* не является нулевым|**EINVAL**|
|*диск* не является**NULL**, *driveNumberOfElements* равен нулю|**EINVAL**|
|*dir* является **NULL**, *dirNumberOfElements* является ненулевым|**EINVAL**|
|*dir* не является**NULL**, *dirNumberOfElements* равен нулю|**EINVAL**|
|*fname* является **NULL**, *nameNumberOfElements* не является нулевым|**EINVAL**|
|*fname* не является**NULL**, *nameNumberOfElements* равен нулю|**EINVAL**|
|*ext* является **NULL**, *extNumberOfElements* не является нулевым|**EINVAL**|
|*ext* не является**NULL**, *extNumberOfElements* равен нулю|**EINVAL**|

Если выполняется какое-либо из приведенных выше условий, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **EINVAL**.

Если какой-либо из буферов слишком короткий, чтобы удерживать результат, эти функции очищают все буферы до пустых строк, устанавливают **errno** в **ERANGE**и возвращают **ERANGE.**

## <a name="remarks"></a>Remarks

Функция **_splitpath_s** разрывает путь на четыре компонента. **_splitpath_s** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтовым кодом, который используется в настоящее время. **_wsplitpath_s** является широкохарактерным вариантом **_splitpath_s;** аргументы в **_wsplitpath_s** являются широкохарактерными строками. В остальном эти функции ведут себя одинаково.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

Каждый компонент полного пути хранится в отдельном буфере; манифест константы **_MAX_DRIVE,** **_MAX_DIR,** **_MAX_FNAME**и **_MAX_EXT** (определяется в STDLIB. H) указать максимально допустимый размер для каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

В приведенной ниже таблице перечислены значения констант манифеста.

|name|Значение|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

Если полный путь не содержит компонента (например, имя файла), **_splitpath_s** присваивает пустую строку соответствующему буферу.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
