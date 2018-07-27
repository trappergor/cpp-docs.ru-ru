---
title: free | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- free
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
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc6dfd832d18dbabc1ebc10aec252cc8afe15346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402521"
---
# <a name="free"></a>free

Освобождает блок памяти.

## <a name="syntax"></a>Синтаксис

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock* ранее выделенный блок памяти, освобождаемой.

## <a name="remarks"></a>Примечания

**Свободного** функция освобождает блок памяти (*memblock*) который был выделен ранее вызовом **calloc**, **malloc**, или **realloc**. Число освобожденных байтов эквивалентно количеству байтов, запрошенному при блок был выделен (или выделении заново, в случае использования **realloc**). Если *memblock* — **NULL**, указатель обрабатывается и **свободного** немедленно возвращает. Попытка освободить недопустимый указатель (указатель на блок памяти, которая не была выделена **calloc**, **malloc**, или **realloc**) может повлиять на последующие запросы выделения памяти и привести к ошибкам.

Если произошла ошибка при освобождении памяти, **errno** задаются сведения из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

После освобождения блока памяти функция [_heapmin](heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.

Когда приложение связано с отладочной версией библиотеки времени выполнения C **свободного** разрешается [_free_dbg](free-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**Бесплатные** помечен `__declspec(noalias)`, это означает, что функция гарантированно не изменит глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

Для освобождения памяти, которая выделена функцией [_malloca](malloca.md), используйте функцию [_freea](freea.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**free**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [malloc](malloc.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
