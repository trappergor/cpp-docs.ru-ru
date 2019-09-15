---
title: _unlock_file
ms.date: 11/04/2016
api_name:
- _unlock_file
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _unlock_file
- unlock_file
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
ms.openlocfilehash: 2983408f066ea00c0b7ab111d9a6349700ecaece
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957478"
---
# <a name="_unlock_file"></a>_unlock_file

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

Функция **_unlock_file** разблокирует файл, указанный в *файле*. Снятие блокировки файла разрешает доступ к этому файлу других процессов. Эта функция не должна вызываться, если ранее не вызывался метод **_lock_file** для указателя на *файл* . Вызов **_unlock_file** для файла, который не заблокирован, может привести к взаимоблокировке. Пример см. в разделе [_lock_file](lock-file.md).

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
