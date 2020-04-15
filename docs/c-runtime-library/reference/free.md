---
title: свободный
ms.date: 4/2/2020
api_name:
- free
- _o_free
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
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: eefbe957ce5057b5038f98bc8da8fb2f0bdd3d1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345982"
---
# <a name="free"></a>свободный

Освобождает блок памяти.

## <a name="syntax"></a>Синтаксис

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Ранее выделенный блок памяти, который требуется освободить.

## <a name="remarks"></a>Remarks

**Бесплатная** функция разблокирует блок памяти *(memblock),* который ранее был выделен вызовом **calloc,** **malloc**, или **realloc.** Количество освобожденных байтов эквивалентно количеству байтов, запрошенных при выделении блока (или перераспределенном, в случае **realloc).** Если *memblock* **null,** указатель игнорируется и **бесплатно** немедленно возвращается. Попытка освободить недействительный указатель (указатель на блок памяти, который не был выделен **calloc,** **malloc**, или **realloc)** может повлиять на последующие запросы распределения и вызвать ошибки.

Если происходит ошибка при освобождении памяти, **errno** устанавливается с информацией из операционной системы о характере сбоя. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

После освобождения блока памяти функция [_heapmin](heapmin.md) минимизирует объем свободной памяти в куче путем объединения неиспользуемых областей и возврата их операционной системе. Освобожденная память, которая не возвращена операционной системе, возвращается в пул свободной памяти и снова доступна для выделения.

Когда приложение связано с отладкой версии библиотек исправления C, **бесплатно** разрешает [_free_dbg.](free-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**бесплатно** помечена, `__declspec(noalias)`что означает, что функция гарантированно не изменяет глобальные переменные. Дополнительные сведения см. в разделе [noalias](../../cpp/noalias.md).

Для освобождения памяти, которая выделена функцией [_malloca](malloca.md), используйте функцию [_freea](freea.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**Бесплатный**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [malloc](malloc.md).

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
