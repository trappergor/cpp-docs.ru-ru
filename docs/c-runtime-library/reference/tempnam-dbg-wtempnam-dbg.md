---
title: _tempnam_dbg, _wtempnam_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
apitype: DLLExport
f1_keywords:
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28b917ce2f50d9b766fd305f3320664d11e93da2
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg

Функциональные версии [_tempnam _wtempnam, tmpnam _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) , которые используют отладочную версию **malloc**, **_malloc_dbg**.

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

*dir*<br/>
Путь, используемый в имени файла, если переменная среды TMP отсутствует или TMP не является допустимым каталогом.

*Префикс*<br/>
Строка, которая добавляется в начало имен, возвращаемых **_tempnam**.

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения или **NULL**.

*linenumber*<br/>
Номер строки в исходном файле, которой была запрошена операция выделения или **NULL**.

## <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает указатель на формируемое имя или **NULL** при неудачном завершении. Ошибка может возникать, если указано недопустимое имя каталога в переменной среды TMP и *dir* параметра.

> [!NOTE]
> **Бесплатные** (или **free_dbg**) необходимо вызывать для указателей, выделенных функциями **_tempnam_dbg** и **_wtempnam_dbg**.

## <a name="remarks"></a>Примечания

**_Tempnam_dbg** и **_wtempnam_dbg** идентичны **_tempnam** и **_wtempnam** за исключением того, что, когда **_DEBUG** будет определено, эти функции используют отладочную версию **malloc** и **_malloc_dbg**для выделения памяти, если **NULL** — передана в качестве первого параметра. Дополнительные сведения см. в разделе [_malloc_dbg](malloc-dbg.md).

Как правило, явно вызывать эти функции не требуется. Вместо этого можно определить флаг **_CRTDBG_MAP_ALLOC**. Когда **_CRTDBG_MAP_ALLOC** определен, вызовы **_tempnam** и **_wtempnam** сопоставляются с **_tempnam_dbg** и **_ wtempnam_dbg**, соответственно, с *blockType* значение **_NORMAL_BLOCK**. Таким образом, не требуется явно вызывать эти функции, если только необходимости пометить блоки кучи как **_CLIENT_BLOCK**. Дополнительные сведения см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

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
