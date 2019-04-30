---
title: _recalloc
ms.date: 11/04/2016
apiname:
- _recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 3bcc238dcb950a8e30af16efc557e99d933efe92
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62357726"
---
# <a name="recalloc"></a>_recalloc

Сочетание **realloc** и **calloc**. Перераспределяет массив в памяти и инициализирует его элементы значением 0.

## <a name="syntax"></a>Синтаксис

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель на ранее выделенный блок памяти.

*номер*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_recalloc** возвращает **void** указатель на блок памяти перераспределенном (и, возможно, перемещенном).

Если имеется достаточно памяти для увеличения блока до заданного размера, исходный блок останется без изменений, и **NULL** возвращается.

Если запрошенный размер равен нулю, то блок, на которые указывают *memblock* , освобождается; возвращается значение **NULL**, и *memblock* прежнему указывает на Освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличное от **void**, используйте приведение типов для возвращаемого значения.

## <a name="remarks"></a>Примечания

**_Recalloc** функция изменяет размер выделенного блока памяти. *Memblock* аргумент указывает на начало блока памяти. Если *memblock* — **NULL**, **_recalloc** ведет себя так же, как [calloc](calloc.md) и выделяет новый блок размером *номер*  *  *размер* байт. Каждый элемент инициализируется значением 0. Если *memblock* не **NULL**, он должен быть указателем, возвращенным предыдущим вызовом **calloc**, [malloc](malloc.md), или [realloc ](realloc.md).

Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный функцией **_recalloc** , не обязательно будет указателем, переданным через *memblock* аргумент.

**_recalloc** задает **errno** для **ENOMEM** если выделение памяти завершается сбоем или количество запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**recalloc** вызовы **realloc** для использования C++ [_set_new_mode](set-new-mode.md) функции, чтобы установить новый режим обработки. Новый режим обработки указывает, что в случае сбоя **realloc** должен вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](set-new-handler.md). По умолчанию **realloc** не вызывает новую подпрограмму обработчика в случае сбоя процесса выделения памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **_recalloc** не удается выделить память, **realloc** вызывала новую подпрограмму обработчика таким же образом, как **новый** оператор выполняет при сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ.

Когда приложение связано с отладочной версией библиотек времени выполнения языка C, **_recalloc** разрешается [_recalloc_dbg](recalloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[Параметры ссылок](../../c-runtime-library/link-options.md)<br/>
