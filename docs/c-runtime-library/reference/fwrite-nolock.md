---
title: _fwrite_nolock
ms.date: 11/04/2016
api_name:
- _fwrite_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fwrite_nolock
- fwrite_nolock
helpviewer_keywords:
- fwrite_nolock function
- streams, writing data to
- _fwrite_nolock function
ms.assetid: 2b4ec6ce-742e-4615-8407-44a0a18ec1d7
ms.openlocfilehash: 035ee1d958c6ea6a13481d92311733ded9ed5f2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956205"
---
# <a name="_fwrite_nolock"></a>_fwrite_nolock

Записывает данные в поток без блокирования потока.

## <a name="syntax"></a>Синтаксис

```C
size_t _fwrite_nolock(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*buffer*<br/>
Указатель на данные, которые требуется записать.

*size*<br/>
Размер элемента в байтах.

*count*<br/>
Максимальное число записываемых элементов.

*вышестоящий*<br/>
Указатель на структуру **FILE**.

## <a name="return-value"></a>Возвращаемое значение

То же, что [fwrite](fwrite.md).

## <a name="remarks"></a>Примечания

Эта функция является версией **fwrite**без блокировки. Он идентичен **fwrite** , за исключением того, что он не защищен от помех в других потоках. Эта функция может выполняться быстрее, поскольку она не создает дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эту функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fwrite_nolock**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [fread](fread.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fread](fread.md)<br/>
[_write](write.md)<br/>
