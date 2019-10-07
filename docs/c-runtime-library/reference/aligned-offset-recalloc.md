---
title: _aligned_offset_recalloc
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: ef8e68622c86e4504745a63cb0c2c3be4e916163
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944139"
---
# <a name="_aligned_offset_recalloc"></a>_aligned_offset_recalloc

Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md), и инициализирует память нулями.

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*Нумерация*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_offset_recalloc** возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение равно **null** , если размер равен нулю, а аргумент буфера не равен **null**, или если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

**_aligned_offset_recalloc** `__declspec(noalias)` помечается `__declspec(restrict)`и, что означает, что функция гарантированно не изменяет глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Примечания

Как и [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_recalloc** позволяет выстроить структуру по смещению в пределах структуры.

**_aligned_offset_recalloc** основан на **malloc**. Дополнительные сведения об использовании **_aligned_offset_malloc**см. в разделе [malloc](malloc.md). Если *мемблокк* имеет **значение NULL**, функция вызывает **_aligned_offset_malloc** внутренним образом.

Эта **функция устанавливает значение** **еномем** , если выделение памяти завершилось ошибкой, или если запрошенный размер (*Размер* *номера* * ) больше **_HEAP_MAXREQ**. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr". Кроме того, **_aligned_offset_recalloc** проверяет свои параметры. Если параметр *alignment* не является степенью 2 или *смещение* больше или равно запрошенному размеру и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **значение NULL** **и устанавливает для** **еинвал**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h>|

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
