---
title: _tempnam_dbg, _wtempnam_dbg
ms.date: 11/04/2016
api_name:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 73642730995ac5c0b47519fac64b30400d47767c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946251"
---
# <a name="_tempnam_dbg-_wtempnam_dbg"></a>_tempnam_dbg, _wtempnam_dbg

Версии функций [_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) , которые используют отладочную версию **malloc**, **_malloc_dbg**.

## <a name="syntax"></a>Синтаксис

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*команды*<br/>
Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.

*prefix*<br/>
Строка, которая будет предваряться именами, возвращаемыми функцией **_tempnam**.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, где была запрошена операция выделения, или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает указатель на созданное имя или **значение NULL** в случае сбоя. Сбой может произойти, если в переменной среды TMP и в параметре *dir* указано недопустимое имя каталога.

> [!NOTE]
> **бесплатный** (или **free_dbg**) необходимо вызывать для указателей, выделенных **_tempnam_dbg** и **_wtempnam_dbg**.

## <a name="remarks"></a>Примечания

Функции **_tempnam_dbg** и **_wtempnam_dbg** идентичны **_tempnam** и **_wtempnam** , за исключением того, что при определении **_DEBUG** эти функции используют отладочную версию функций **malloc** и **_malloc_dbg**, для выделить память, если **значение NULL** передается как первый параметр. Дополнительные сведения см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг **_CRTDBG_MAP_ALLOC**. Если определен **_CRTDBG_MAP_ALLOC** , вызовы методов **_tempnam** и **_wtempnam** пересопоставляются с **_tempnam_dbg** и **_wtempnam_dbg**соответственно, а *блокктипе* устанавливается в **_NORMAL_BLOCK**. Таким образом, не нужно явно вызывать эти функции, если не нужно помечать блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
