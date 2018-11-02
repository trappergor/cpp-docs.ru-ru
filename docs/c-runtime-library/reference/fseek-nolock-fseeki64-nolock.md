---
title: _fseek_nolock, _fseeki64_nolock
ms.date: 11/04/2016
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
ms.openlocfilehash: 57e9a57223d6af620f4f9160923675b4873ab3ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502457"
---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock, _fseeki64_nolock

Перемещает файловый указатель в указанное местоположение.

## <a name="syntax"></a>Синтаксис

```C
int _fseek_nolock(
   FILE *stream,
   long offset,
   int origin
);
int _fseeki64_nolock(
   FILE *stream,
   __int64 offset,
   int origin
);
```

### <a name="parameters"></a>Параметры

*поток*<br/>
Указатель на структуру **FILE**.

*offset*<br/>
Количество байт, начиная с *origin*.

*origin*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

Совпадение с кодом [fseek](fseek-fseeki64.md) и [_fseeki64](fseek-fseeki64.md), соответственно.

## <a name="remarks"></a>Примечания

Эти функции являются неблокирующей версии [fseek](fseek-fseeki64.md) и [_fseeki64](fseek-fseeki64.md), соответственно. Они идентичны [fseek](fseek-fseeki64.md) и [_fseeki64](fseek-fseeki64.md) за исключением того, что они не защищены от помех со стороны других потоков. Они могут выполняться быстрее, так как не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[rewind](rewind.md)<br/>
