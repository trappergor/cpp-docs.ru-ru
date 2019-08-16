---
title: _splitpath, _wsplitpath
ms.date: 11/04/2016
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
ms.openlocfilehash: d5aab68524c0833bff0e09927587c0362c5194f9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500992"
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

*path*<br/>
Полный путь.

*диск*<br/>
Буква диска, за которой следует двоеточие ( **:** ). Если буква диска не нужна, можно передать **значение NULL** для этого параметра.

*команды*<br/>
Путь к каталогу, включая заключительную косую черту. Можно использовать символы косой **/** черты (), обратные косые черты ( **\\** ) или и то, и другое. Если путь к каталогу не требуется, можно передать **значение NULL** для этого параметра.

*fname*<br/>
Базовое имя файла (без расширения). Если имя файла не требуется, можно передать **значение NULL** для этого параметра.

*WLAN*<br/>
Расширение имени файла, включая начальную точку ( **.** ). Если расширение имени файла не требуется, можно передать **значение NULL** для этого параметра.

## <a name="remarks"></a>Примечания

Функция **_splitpath** разбивает путь на четыре компонента. **_splitpath** автоматически обрабатывает строковые аргументы многобайтовых символов соответствующим образом, распознает последовательности многобайтовых символов в соответствии с используемой в данный момент многобайтовой кодовой страницей. **_wsplitpath** — это версия **_splitpath**для расширенных символов; аргументы для **_wsplitpath** являются строками расширенных символов. В остальном эти функции ведут себя одинаково.

**Примечание о безопасности.** Эти функции предполагают потенциальную угрозу, связанную с проблемой переполнения буфера. Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns). Существуют более безопасные версии этих функций; см. раздел [_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

Каждый компонент полного пути хранится в отдельном буфере. константы манифеста **_MAX_DRIVE**, **_MAX_DIR**, **_MAX_FNAME**и **_MAX_EXT** (определяются в STDLIB. З) укажите максимальный размер каждого компонента файла. Компоненты файла, размер которых превышает значения соответствующих констант манифеста, могут вызвать повреждение кучи.

Каждый буфер должен быть соразмерен соответствующей константе манифеста, чтобы избежать потенциального переполнения буфера.

В приведенной ниже таблице перечислены значения констант манифеста.

|name|Значение|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

Если полный путь не содержит компонент (например, имя файла), **_splitpath** присваивает соответствующим буферам пустые строки.

Можно передать **значение NULL** в **_splitpath** для любого параметра, кроме *пути* , который не требуется.

Если параметр *path* имеет **значение NULL**, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено , для параметра **еинвал** задается значение, а функция возвращает **еинвал**.

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
