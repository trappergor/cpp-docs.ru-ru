---
title: _aligned_realloc
ms.date: 11/04/2016
api_name:
- _aligned_realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_realloc
- aligned_realloc
helpviewer_keywords:
- aligned_realloc function
- _aligned_realloc function
ms.assetid: 80ce96e8-6087-416f-88aa-4dbb8cb1d218
ms.openlocfilehash: 34af7d1dc3c5c8e5d504191b18280e228079eaa2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70943813"
---
# <a name="_aligned_realloc"></a>_aligned_realloc

Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_realloc(
   void *memblock,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*size*<br/>
Размер запрошенного выделения памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_realloc** возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение равно **null** , если размер равен нулю, а аргумент буфера не равен **null**, или если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

Будет ошибкой повторно выделить память и изменить выравнивание блока.

## <a name="remarks"></a>Примечания

**_aligned_realloc** основан на **malloc**. Дополнительные сведения об использовании **_aligned_offset_malloc**см. в разделе [malloc](malloc.md).

Эта **функция устанавливает** **еномем** в случае сбоя выделения памяти или если запрошенный размер был больше **_HEAP_MAXREQ**. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr". Кроме того, **_aligned_realloc** проверяет свои параметры. Если значение *alignment* не является степенью числа 2, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **значение NULL** **и устанавливает для** **еинвал**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_realloc**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
