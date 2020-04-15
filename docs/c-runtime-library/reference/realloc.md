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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 964c465a95d44de9d8a4d399f23ec43f8a3a6692
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332935"
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

*Размер*<br/>
Новый размер в байтах.

## <a name="return-value"></a>Возвращаемое значение

**realloc** возвращает **пустоту** указателя на перераспределенный (и, возможно, перемещенный) блок памяти.

Если не хватает доступной памяти, чтобы расширить блок до данного размера, исходный блок остается неизменным, и **NULL** возвращается.

Если *размер* равен нулю, то блок, на который указывает *memblock,* освобождается; значение возврата **NULL,** и *memblock* остается указывая на освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, не **превышающие пустоты,** используйте тип, отлитый на значении возврата.

## <a name="remarks"></a>Remarks

Функция **realloc** изменяет размер выделенного блока памяти. Аргумент *memblock* указывает на начало блока памяти. Если *memblock* **null,** **realloc** ведет себя так же, как **malloc** и выделяет новый блок *размера* байтов. Если *memblock* не **является NULL,** он должен быть указатель вернулся предыдущий звонок **calloc**, **malloc**, или **realloc**.

Аргумент *размера* дает новый размер блока, в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным, хотя новый блок может находиться в другом расположении. Поскольку новый блок может находиться в новом месте памяти, указатель, возвращенный **realloc,** не гарантируется указателем, пройденым через аргумент *memblock.* **realloc** не обнуляет вновь выделенную память в случае роста буфера.

**realloc** устанавливает **errno** для **ENOMEM,** если выделение памяти не удается или если количество запрошенной памяти превышает **_HEAP_MAXREQ.** Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**realloc** вызывает **malloc** для того, чтобы использовать функцию [_set_new_mode](set-new-mode.md) СЗ для установки нового режима обработчика. Новый режим обработчика указывает, является ли, при сбое, **malloc** является вызов новой рутины обработчика, как установить [_set_new_handler.](set-new-handler.md) По умолчанию **malloc** не вызывает новую рутину обработчика при неспособности выделить память. Вы можете переопределить это поведение по умолчанию, чтобы, когда **realloc** не выделяет память, **malloc** вызывает новую рутину обработчика так же, как **новый** оператор делает, когда он не по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием NEWMODE.OBJ (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Когда приложение связано с отладкой версии библиотек исправления C, **realloc** решает [_realloc_dbg.](realloc-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**realloc** отмечен `__declspec(noalias)` `__declspec(restrict)`и , что означает, что функция гарантированно не изменять глобальные переменные, и что указатель вернулся не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Бесплатный](free.md)<br/>
[malloc](malloc.md)<br/>
