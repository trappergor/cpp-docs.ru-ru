---
title: realloc
ms.date: 4/2/2020
api_name:
- realloc
- _o_realloc
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 72c38021452940553bad770160ecc5db7ea546d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216821"
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

метод **realloc** возвращает **`void`** указатель на перераспределенный (и, возможно, перемещенный) блок памяти.

Если недостаточно памяти для расширения блока до заданного размера, исходный блок остается без изменений и возвращается **значение NULL** .

Если *Размер* равен нулю, то блок, на который указывает *мемблокк* , освобождается; Возвращаемое значение равно **null**, и *мемблокк* остается указывающим на освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличный от **`void`** , используйте приведение типа к возвращаемому значению.

## <a name="remarks"></a>Remarks

Функция **realloc** изменяет размер выделенного блока памяти. Аргумент *мемблокк* указывает на начало блока памяти. Если *мемблокк* имеет **значение NULL**, перераспределение ведет себя таким же образом, как и **malloc** **, и** выделяет новый блок *размером* байтов. Если *мемблокк* не равно **null**, это должен быть указатель, возвращенный предыдущим вызовом метода **calloc**, **malloc**или **realloc**.

Аргумент *size* задает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным, хотя новый блок может находиться в другом расположении. Так как новый блок может находиться в новом месте в памяти, указатель, возвращаемый методом **realloc** , не обязательно должен быть указателем, передаваемым через аргумент *мемблокк* . перераспределение **не приводит к** обнулению памяти в случае роста буфера.

наборы **перераспределения** имеют значение **еномем** **, если** выделение памяти завершается неудачей или объем запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**перераспределения** вызывают **malloc** для использования функции [_set_new_mode](set-new-mode.md) C++ для установки нового режима обработчика. Новый режим обработчика указывает, что в случае сбоя **malloc** вызывает новую подпрограммы обработчика, заданную [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, чтобы при перераспределении **не удалось выделить** память, **malloc** вызывает новую подпрограммы обработчика таким же образом, как это **`new`** делает оператор в случае сбоя по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием NEWMODE.OBJ (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Если приложение связано с отладочной версией библиотек времени выполнения C, **перераспределения** разрешается в [_realloc_dbg](realloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**Переопределение помечено** как `__declspec(noalias)` и `__declspec(restrict)` , что означает, что функция гарантированно не изменяет глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**realloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[свободный](free.md)<br/>
[malloc](malloc.md)<br/>
