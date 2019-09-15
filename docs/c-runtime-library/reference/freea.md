---
title: _freea
ms.date: 11/04/2016
api_name:
- _freea
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: dcad8bea4f8cec28d8cb15a9937b1032593ef0cc
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956712"
---
# <a name="_freea"></a>_freea

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

Нет.

## <a name="remarks"></a>Примечания

Функция **_freea** освобождает блок памяти (*мемблокк*), который был ранее выделен вызовом [_malloca](malloca.md). **_freea** проверяет, была ли память выделена в куче или стеке. Если он был выделен в стеке, **_freea** не выполняет никаких действий. Если память выделена в куче, число освобожденных байтов эквивалентно количеству байтов, запрошенному при выделении блока. Если *мемблокк* имеет **значение NULL**, указатель игнорируется и **_freea** немедленно возвращает значение. Попытка освободить недопустимый указатель (указатель на блок памяти, который не был выделен **_malloca**) может повлиять на последующие запросы на выделение и привести к ошибкам.

**_freea** вызывает **Free** , если обнаруживает, что память выделена в куче. Информация о том, выделена ли память в куче или в стеке, определяется меткой, которая устанавливается в памяти по адресу, непосредственно предшествующему выделенному блоку памяти.

Если при освобождении памяти произошла ошибка, то параметру "очистить" **задается** информация из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

После освобождения блока памяти функция [_heapmin](heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.

Вызов **_freea** должен сопровождать все вызовы к **_malloca**. Также возникает ошибка вызова **_freea** дважды в одной и той же памяти. Если приложение связано с отладочной версией библиотек времени выполнения C, особенно с включенными функциями [_malloc_dbg](malloc-dbg.md) путем определения **_CRTDBG_MAP_ALLOC**, проще обнаружить отсутствующие или дублирующиеся вызовы **_freea**. Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**_freea** помечается `__declspec(noalias)`, то есть гарантируется, что функция не будет изменять глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

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
