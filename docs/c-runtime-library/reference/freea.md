---
title: _freea | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _freea
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
apitype: DLLExport
f1_keywords:
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac01f965e159dae19bbbd748c1692058063a211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403607"
---
# <a name="freea"></a>_freea

Освобождает блок памяти.

## <a name="syntax"></a>Синтаксис

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Ранее выделенный блок памяти, который требуется освободить.

## <a name="return-value"></a>Возвращаемое значение

Отсутствует.

## <a name="remarks"></a>Примечания

**_Freea** функция освобождает блок памяти (*memblock*) который был выделен ранее вызовом [_malloca](malloca.md). **_freea** проверяет, если объем памяти был выделен в куче или стека. Если он выделен в стеке, **_freea** не выполняет никаких действий. Если память выделена в куче, число освобожденных байтов эквивалентно количеству байтов, запрошенному при выделении блока. Если *memblock* — **NULL**, указатель обрабатывается и **_freea** немедленно возвращает. Попытка освободить недопустимый указатель (указатель на блок памяти, которая не была выделена **_malloca**) может повлиять на последующие запросы выделения памяти и привести к ошибкам.

**_freea** вызовы **свободного** внутренним образом в том случае, если обнаруживается, что память выделяется в куче. Информация о том, выделена ли память в куче или в стеке, определяется меткой, которая устанавливается в памяти по адресу, непосредственно предшествующему выделенному блоку памяти.

Если произошла ошибка при освобождении памяти, **errno** задаются сведения из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

После освобождения блока памяти функция [_heapmin](heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.

Вызов **_freea** должны сопровождаться экранирующим все вызовы **_malloca**. Это ошибка для вызова **_freea** дважды в одной и той же памяти. Когда приложение связано с отладочной версией библиотеки времени выполнения C, особенно с [_malloc_dbg](malloc-dbg.md) функции, доступные при определении **_CRTDBG_MAP_ALLOC**, проще найти отсутствующую или повторяющиеся вызовы **_freea**. Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**_freea** помечен `__declspec(noalias)`, это означает, что функция гарантированно не изменит глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_freea**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [_malloca](malloca.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
