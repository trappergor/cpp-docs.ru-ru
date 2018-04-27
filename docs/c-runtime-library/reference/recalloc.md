---
title: _recalloc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a87aa06cecd27db22354108f283802775f62b02e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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

*Номер*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_recalloc** возвращает **void** указатель на блок памяти перераспределенный (и, возможно, перемещенный).

Если недостаточно памяти для расширения блока до заданного размера, исходный блок останется без изменений, и **NULL** возвращается.

Если запрошенный размер равен нулю, то блок, на который указывает *memblock* , освобождается; возвращается значение **NULL**, и *memblock* указывать на Освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличный от **void**, используйте приведение типа для возвращаемого значения.

## <a name="remarks"></a>Примечания

**_Recalloc** функция изменяет размер выделенного блока памяти. *Memblock* аргумент указывает на начало блока памяти. Если *memblock* — **NULL**, **_recalloc** ведет себя так же, как [calloc](calloc.md) и выделяет новый блок *номер*  *  *размер* байт. Каждый элемент инициализируется значением 0. Если *memblock* не **NULL**, он должен быть указателем, возвращенным предыдущим вызовом **calloc**, [malloc](malloc.md), или [realloc ](realloc.md).

Поскольку новый блок может находиться в новом расположении памяти, указатель, возвращенный функцией **_recalloc** , не обязательно будет указателем, переданным через *memblock* аргумент.

**_recalloc** задает **errno** для **ENOMEM** если выделение памяти завершается сбоем или количество запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**recalloc** вызовы **realloc** для использования функции C++ [_set_new_mode](set-new-mode.md) функции, чтобы установить новый режим обработки. Новый режим обработки указывает, что в случае сбоя **realloc** является вызов новую подпрограмму обработчика задается [_set_new_handler](set-new-handler.md). По умолчанию **realloc** не вызывать новую подпрограмму обработчика сбои при выделении памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **_recalloc** не удается выделить память, **realloc** вызывает новую подпрограмму обработчика так же, как **новый** оператор При сбое по той же причине выполняет. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ.

Когда приложение связано с отладочной версией библиотеки времени выполнения C **_recalloc** разрешается [_recalloc_dbg](recalloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные и возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

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
