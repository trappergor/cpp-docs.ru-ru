---
title: _recalloc
ms.date: 4/2/2020
api_name:
- _recalloc
- _o__recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 57972a48336d8dd362b5da7513c854703134921b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338124"
---
# <a name="_recalloc"></a>_recalloc

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

*число*<br/>
Число элементов.

*Размер*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_recalloc** возвращает **недействительный** указатель на перераспределенный (и, возможно, перемещенный) блок памяти.

Если не хватает доступной памяти, чтобы расширить блок до данного размера, исходный блок остается неизменным, и **NULL** возвращается.

Если запрашиваемый размер равен нулю, то блок, на который указывает *memblock,* освобождается; значение возврата **NULL,** и *memblock* остается указывая на освобожденный блок.

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, не **превышающие пустоты,** используйте тип, отлитый на значении возврата.

## <a name="remarks"></a>Remarks

Функция **_recalloc** изменяет размер выделенного блока памяти. Аргумент *memblock* указывает на начало блока памяти. Если *memblock* **null,** **_recalloc** ведет себя так же, как [calloc](calloc.md) и выделяет новый блок*байтов размера* *числа.* *  Каждый элемент инициализируется значением 0. Если *memblock* не **является NULL,** он должен быть указатель вернулся предыдущий звонок **calloc**, [malloc](malloc.md), или [realloc](realloc.md).

Поскольку новый блок может находиться в новом месте памяти, указатель, возвращенный **_recalloc** не гарантируется указателем, пройденым через аргумент *memblock.*

**_recalloc** устанавливает **errno** в **ENOMEM,** если выделение памяти не удается или если количество запрошенной памяти превышает **_HEAP_MAXREQ.** Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**recalloc** вызывает **realloc** для того, чтобы использовать функцию [_set_new_mode](set-new-mode.md) сот., чтобы установить новый режим обработчика. Новый режим обработчика указывает, должен ли **realloc** вызвать новую рутину обработчика в установленный [_set_new_handler.](set-new-handler.md) По умолчанию **realloc** не вызывает новую рутину обработчика при неспособности выделить память. Это поведение по умолчанию можно переопределить таким образом, чтобы при **_recalloc** не удавалось выделить память, **realloc** вызывает новую процедуру обработчика так же, как это делает **новый** оператор, когда он выходит из строя по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ.

Когда приложение связано с отладкой версии библиотек исправления C, **_recalloc** решает [_recalloc_dbg.](recalloc-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** помечения `__declspec(noalias)` и, `__declspec(restrict)`что означает, что функция гарантированно не изменяет глобальные переменные, и что указатель возвращается не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[Бесплатный](free.md)<br/>
[Параметры ссылок](../../c-runtime-library/link-options.md)<br/>
