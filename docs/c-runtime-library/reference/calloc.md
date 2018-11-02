---
title: calloc
ms.date: 11/04/2016
apiname:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 59aa535136cf32ea5dd68b8917ec969eee41e2ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666977"
---
# <a name="calloc"></a>calloc

Выделяет массив в памяти и инициализирует его элементы значением 0.

## <a name="syntax"></a>Синтаксис

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**calloc** возвращает указатель на выделенную память. Пространство в хранилище, на которое указывает возвращаемое значение, гарантированно выровнено подходящим для хранения любого типа объектов образом. Чтобы получить указатель на тип, отличное от **void**, используйте приведение типов для возвращаемого значения.

## <a name="remarks"></a>Примечания

**Calloc** функция выделяет пространство для хранения массива *номер* элементов, каждый из длина *размер* байт. Каждый элемент инициализируется значением 0.

**calloc** задает **errno** для **ENOMEM** если выделение памяти завершается сбоем или количество запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**calloc** вызовы **malloc** использовать C++ [_set_new_mode](set-new-mode.md) функции, чтобы установить новый режим обработки. Новый режим обработки указывает, что в случае сбоя **malloc** должен вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограмму обработчика в случае сбоя процесса выделения памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **calloc** не удается выделить память, **malloc** вызывала новую подпрограмму обработчика таким же образом, как **новый** делает оператор При сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или выполните компоновку с использованием NEWMODE.OBJ (см. раздел [Параметры ссылок](../../c-runtime-library/link-options.md)).

Когда приложение связано с отладочной версией библиотек времени выполнения языка C, **calloc** разрешается [_calloc_dbg](calloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**calloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

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
