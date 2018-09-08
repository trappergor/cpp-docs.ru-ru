---
title: _unlock_file | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _unlock_file
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
- _unlock_file
- unlock_file
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63b0950aaea5520849f9a32b2b08ab138cd8099b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107551"
---
# <a name="unlockfile"></a>_unlock_file

Разблокирует файл, разрешая к нему доступ других процессов.

## <a name="syntax"></a>Синтаксис

```C
void _unlock_file(
   FILE* file
);
```

### <a name="parameters"></a>Параметры

*file*<br/>
Дескриптор файла.

## <a name="remarks"></a>Примечания

**_Unlock_file** функция разблокирует файл, указанный параметром *файл*. Снятие блокировки файла разрешает доступ к этому файлу других процессов. Эта функция не должны вызываться, если не **_lock_file** был ранее вызван для *файл* указатель. Вызов **_unlock_file** в файле, который не будет заблокирован, могут привести к взаимоблокировке. Пример см. в разделе [_lock_file](lock-file.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_unlock_file**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Обработка файлов](../../c-runtime-library/file-handling.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_lock_file](lock-file.md)<br/>
