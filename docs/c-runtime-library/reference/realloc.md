---
title: realloc
ms.date: 11/04/2016
apiname:
- realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
ms.openlocfilehash: 0d61746365a8ded8d68072b1f398a18ba6ce7605
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544967"
---
# <a name="realloc"></a>realloc

Повторное выделение блоков памяти.

## <a name="syntax"></a>Синтаксис

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель на ранее выделенный блок памяти.

*size*<br/>
Новый размер в байтах.

## <a name="return-value"></a>Возвращаемое значение

**realloc** возвращает **void** указатель на блок памяти перераспределенном (и, возможно, перемещенном).

Если имеется достаточно памяти для увеличения блока до заданного размера, исходный блок останется без изменений, и **NULL** возвращается.

Если *размер* равно нулю, то блок, на которые указывают *memblock* , освобождается; возвращается значение **NULL**, и *memblock* прежнему указывает на Освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличное от **void**, используйте приведение типов для возвращаемого значения.

## <a name="remarks"></a>Примечания

**Realloc** функция изменяет размер выделенного блока памяти. *Memblock* аргумент указывает на начало блока памяти. Если *memblock* — **NULL**, **realloc** ведет себя так же, как **malloc** и выделяет новый блок размером *размер*байт. Если *memblock* не **NULL**, он должен быть указателем, возвращенным предыдущим вызовом **calloc**, **malloc**, или **realloc** .

*Размер* аргумент указывает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным, хотя новый блок может находиться в другом расположении. Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный функцией **realloc** , не обязательно будет указателем, переданным через *memblock* аргумент. **realloc** не отлично от нуля вновь выделенной памяти в случае роста буфера.

**realloc** задает **errno** для **ENOMEM** если выделение памяти завершается сбоем или количество запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**realloc** вызовы **malloc** для использования C++ [_set_new_mode](set-new-mode.md) функции, чтобы установить новый режим обработки. Новый режим обработки указывает, что в случае сбоя **malloc** должен вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограмму обработчика в случае сбоя процесса выделения памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **realloc** не удается выделить память, **malloc** вызывала новую подпрограмму обработчика таким же образом, как **новый** делает оператор При сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием NEWMODE.OBJ (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Когда приложение связано с отладочной версией библиотек времени выполнения языка C, **realloc** разрешается [_realloc_dbg](realloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**realloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**realloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
