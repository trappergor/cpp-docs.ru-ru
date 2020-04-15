---
title: _fseek_nolock, _fseeki64_nolock
ms.date: 4/2/2020
api_name:
- _fseek_nolock
- _fseeki64_nolock
- _o__fseek_nolock
- _o__fseeki64_nolock
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 3533e7897e9c460d3be73b8907a6bd3c96f6888f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345737"
---
# <a name="_fseek_nolock-_fseeki64_nolock"></a>_fseek_nolock, _fseeki64_nolock

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

*Поток*<br/>
Указатель на структуру **FILE**.

*Смещение*<br/>
Количество байт, начиная с *origin*.

*Происхождения*<br/>
Первоначальная позиция.

## <a name="return-value"></a>Возвращаемое значение

То же самое, что [fseek](fseek-fseeki64.md) и [_fseeki64,](fseek-fseeki64.md)соответственно.

## <a name="remarks"></a>Remarks

Эти функции являются неблокирующих версий [fseek](fseek-fseeki64.md) и [_fseeki64,](fseek-fseeki64.md)соответственно. Они идентичны [fseek](fseek-fseeki64.md) и [_fseeki64](fseek-fseeki64.md) за исключением того, что они не защищены от помех другими потоками. Они могут выполняться быстрее, так как не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_fseek_nolock**, **_fseeki64_nolock**|\<stdio.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[Перемотки](rewind.md)<br/>
