---
title: _splitpath, _wsplitpath | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69123bfd07d992d96c504e538ded157c49991dab
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221612"
---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath

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

*путь* полный путь.

*диск* букву диска, за которым следует двоеточие (**:**). Вы можете передать **NULL** для этого параметра, если буква диска не требуется.

*dir* путь к каталогу, включая заключительную косую черту. Символ косой черты ( **/** ), обратной косой черты ( **\\** ), или оба могут использоваться. Вы можете передать **NULL** для этого параметра, если путь к каталогу не требуется.

*fname* базового имени файла (без расширения). Вы можете передать **NULL** для этого параметра, если имя файла не требуется.

*ext* расширение имени файла, включая ведущую точку (**.**). Вы можете передать **NULL** для этого параметра, если расширение имени файла не требуется.

## <a name="remarks"></a>Примечания

**_Splitpath** функция разделяет путь на четыре компонента. **_splitpath** автоматически обрабатывает многобайтовые строковые аргументы должным образом, распознавая последовательности многобайтовых символов согласно многобайтовой кодовой странице в настоящий момент. **_wsplitpath** — это двухбайтовая версия **_splitpath**; аргументы для **_wsplitpath** представляют собой строки расширенных символов. В остальном эти функции ведут себя одинаково.

**Примечание о безопасности.** Эти функции предполагают потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns). Существуют более безопасные версии этих функций; см. раздел [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Каждый компонент полного пути сохраняется в отдельном буфере; константы манифеста **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**, и **_MAX_EXT** (определенных в STDLIB. H) укажите максимальный размер каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

Каждый буфер должен быть соразмерен соответствующей константе манифеста, чтобы избежать потенциального переполнения буфера.

В приведенной ниже таблице перечислены значения констант манифеста.

|name|Значение|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Если полный путь не содержит некоторый компонент (например, имя файла), **_splitpath** назначает пустые строки в соответствующий буферы.

Вы можете передать **NULL** для **_splitpath** для любого параметра, отличное от *путь* , не требуется.

Если *путь* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [_makepath](makepath-wmakepath.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
