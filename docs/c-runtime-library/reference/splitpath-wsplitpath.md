---
title: _splitpath, _wsplitpath
ms.date: 4/2/2020
api_name:
- _wsplitpath
- _splitpath
- _o__splitpath
- _o__wsplitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
ms.openlocfilehash: 6798f93b2d1bc18a190b3b015bf8c882a3fa8a37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355611"
---
# <a name="_splitpath-_wsplitpath"></a>_splitpath, _wsplitpath

Разбивают имя пути на компоненты. Существуют более безопасные версии этих функций; см. раздел [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

## <a name="syntax"></a>Синтаксис

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>Параметры

*Путь*<br/>
Полный путь.

*Диске*<br/>
Привод письмо, а затем толстой кишки (**:**). Вы можете пройти **NULL** для этого параметра, если вам не нужно письмо диска.

*dir*<br/>
Путь к каталогу, включая заключительную косую черту. Передние **/** слэши ( **\\** ), backslashes ( ), или оба могут быть использованы. Вы можете пройти **NULL** для этого параметра, если вам не нужен путь каталога.

*Fname*<br/>
Базовое имя файла (без расширения). Вы можете пройти **NULL** для этого параметра, если вам не нужно имя файла.

*Ext*<br/>
Продление Filename, включая опережая **(. ).** Вы можете пройти **NULL** для этого параметра, если вам не нужно расширение имя файла.

## <a name="remarks"></a>Remarks

Функция **_splitpath** разрывает путь на четыре компонента. **_splitpath** автоматически обрабатывает аргументы строки мультибайт-символа по мере необходимости, распознавая последовательности мультибайт-символов в соответствии с многобайтовым кодом, который используется в настоящее время. **_wsplitpath** является широкохарактерным вариантом **_splitpath;** аргументы в **_wsplitpath** являются широкохарактерными строками. В остальном эти функции ведут себя одинаково.

**Примечание о безопасности.** Эти функции предполагают потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns). Доступны более безопасные версии этих функций; увидеть [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Каждый компонент полного пути хранится в отдельном буфере; манифест константы **_MAX_DRIVE,** **_MAX_DIR,** **_MAX_FNAME**и **_MAX_EXT** (определяется в STDLIB. H) указать максимальный размер для каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

Каждый буфер должен быть соразмерен соответствующей константе манифеста, чтобы избежать потенциального переполнения буфера.

В приведенной ниже таблице перечислены значения констант манифеста.

|name|Значение|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Если полный путь не содержит компонента (например, имя файла), **_splitpath** присваивает соответствующим буферам пустые строки.

Вы можете передать **NULL** **_splitpath** для любого параметра, кроме *пути,* который вам не нужен.

Если *путь* **NULL,** вызовуется недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>См. также раздел

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
