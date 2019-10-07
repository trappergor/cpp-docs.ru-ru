---
title: _fullpath_dbg, _wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: 9271e26bcf4a78ff8d2e4fcf108f1e483c22c1d7
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956315"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg, _wfullpath_dbg

Версии [_fullpath, _wfullpath](fullpath-wfullpath.md) , использующие отладочную версию функции **malloc** для выделения памяти.

## <a name="syntax"></a>Синтаксис

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*абспас*<br/>
Указатель на буфер, содержащий абсолютный или полный путь, или **значение NULL**.

*релпас*<br/>
Относительный путь.

*maxLength*<br/>
Максимальная длина абсолютного буфера имени пути (*абспас*). Это длина в байтах для **_fullpath** , но в расширенных символах (**wchar_t**) для **_wfullpath**.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция выделения, или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает указатель на буфер, содержащий абсолютный путь (*абспас*). Если возникает ошибка (например, если значение, передаваемое в *релпас* , содержит букву диска, которая не является допустимой или не может быть найдена, или длина созданного абсолютного пути (*абспас*) больше, чем *MaxLength*), функция возвращает  **Значение NULL**.

## <a name="remarks"></a>Примечания

Функции **_fullpath_dbg** и **_wfullpath_dbg** идентичны **_fullpath** и **_wfullpath** , за исключением того, что при определении **_DEBUG** эти функции используют отладочную версию **malloc**, **_malloc_dbg**, выделение памяти, если **значение NULL** передается как первый параметр. Сведения о функциях отладки **_malloc_dbg**см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг **_CRTDBG_MAP_ALLOC** . Если определен **_CRTDBG_MAP_ALLOC** , вызовы методов **_fullpath** и **_wfullpath** пересопоставляются с **_fullpath_dbg** и **_wfullpath_dbg**соответственно, а *блокктипе* устанавливается в **_NORMAL_BLOCK**. Таким образом, не нужно явно вызывать эти функции, если не нужно помечать блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
