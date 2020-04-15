---
title: calloc
description: Функция библиотеки синхронизирования C-службы calloc выделяет нулевым инициализированным памятью.
ms.date: 4/2/2020
api_name:
- calloc
- _o_calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: fb4f7d6dc059023d34cb0b811edf5dfb48cb7a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333650"
---
# <a name="calloc"></a>calloc

Выделяет массив в памяти и инициализирует его элементы значением 0.

## <a name="syntax"></a>Синтаксис

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>Параметры

*число*<br/>
Число элементов.

*Размер*<br/>
Длина каждого элемента в байтах.

## <a name="return-value"></a>Возвращаемое значение

**calloc** возвращает указатель в выделенное пространство. Пространство в хранилище, на которое указывает возвращаемое значение, гарантированно выровнено подходящим для хранения любого типа объектов образом. Чтобы получить указатель на тип, не **превышающие пустоты,** используйте тип, отлитый на значении возврата.

## <a name="remarks"></a>Remarks

Функция **calloc** выделяет пространство для хранения множества *элементов,* каждый из *байтов размера* длины. Каждый элемент инициализируется значением 0.

**calloc** устанавливает **errno** в **ENOMEM,** если выделение памяти не удается или если количество запрошенной памяти превышает **_HEAP_MAXREQ.** Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

В реализации Майкрософт, если *число* или *размер* равны нулю, **calloc** возвращает указатель на выделенный блок ненулевого размера. Попытка прочитать или написать через возвращенный указатель приводит к неопределенному поведению.

**calloc** использует функцию [_set_new_mode](set-new-mode.md) сс для установки *нового режима обработчика.* Новый режим обработчика указывает, должен ли **calloc** вызывать новую рутину обработчика в установленный [_set_new_handler.](set-new-handler.md) По умолчанию **calloc** не называет новую рутину обработчика при неспособности выделить память. Это поведение по умолчанию можно переопределить таким образом, чтобы, когда **calloc** не выделял память, он называет новую рутину обработчика так же, как это делает **новый** оператор, когда он выходит из строя по той же причине. Чтобы переопределить значение по умолчанию, вызовите

```C
_set_new_mode(1);
```

в начале вашей программы, или ссылку с *NEWMODE. OBJ* (см. [Варианты ссылки).](../../c-runtime-library/link-options.md)

Когда приложение связано с отладкой версии библиотек исправления C, **calloc** решает [_calloc_dbg.](calloc-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**calloc** отмечен `__declspec(noalias)` `__declspec(restrict)`и, что означает, что функция гарантированно не изменяет глобальные переменные, и что указатель вернулся не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**calloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[Бесплатный](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
