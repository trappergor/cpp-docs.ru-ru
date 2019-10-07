---
title: calloc
description: Функция библиотеки времени выполнения C calloc выделяет нуль-инициализированную память.
ms.date: 09/27/2019
api_name:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 228ec6d01a6f57ff98a9030f5a6d82e4c57388cd
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685364"
---
# <a name="calloc"></a>calloc

Выделяет массив в памяти и инициализирует его элементы значением 0.

## <a name="syntax"></a>Синтаксис

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*Нумерация*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**calloc** возвращает указатель на выделенное пространство. Пространство в хранилище, на которое указывает возвращаемое значение, гарантированно выровнено подходящим для хранения любого типа объектов образом. Чтобы получить указатель на тип, отличный от **void**, используйте приведение типа к возвращаемому значению.

## <a name="remarks"></a>Примечания

Функция **calloc** выделяет место для хранения массива *числовых* элементов, каждый из которых имеет *Размер* в байтах. Каждый элемент инициализируется значением 0.

**calloc** устанавливает **значение** переводится в **еномем** , если выделение памяти завершается ошибкой или если объем запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В реализации Майкрософт, если *Number* или *size* равны нулю, **calloc** возвращает указатель на выделенный блок ненулевого размера. Попытка чтения или записи по возвращенному указателю приводит к неопределенному поведению.

**calloc** использует C++ функцию [_set_new_mode](set-new-mode.md) для установки *нового режима обработчика*. Новый режим обработчика указывает, будет ли в случае сбоя **calloc** вызывать новую подпрограммы обработчика, установленную [_set_new_handler](set-new-handler.md). По умолчанию **calloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что, когда **calloc** не сможет выделить память, он вызывает новую подпрограммы обработчика так же, как и оператор **New** в случае сбоя по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или свяжите с *использованием NEWMODE. OBJ* (см. раздел [Параметры связи](../../c-runtime-library/link-options.md)).

Если приложение связано с отладочной версией библиотек времени выполнения C, **calloc** разрешается в [_calloc_dbg](calloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**calloc** помечается `__declspec(noalias)` и `__declspec(restrict)`, то есть гарантируется, что функция не будет изменять глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**calloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
