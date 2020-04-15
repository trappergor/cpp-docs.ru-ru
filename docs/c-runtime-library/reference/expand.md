---
title: _expand
ms.date: 4/2/2020
api_name:
- _expand
- _o__expand
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
- _bexpand
- fexpand
- expand
- nexpand
- _fexpand
- _nexpand
- bexpand
- _expand
helpviewer_keywords:
- memory blocks, changing size
- _expand function
- expand function
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
ms.openlocfilehash: 7f2a789bc5f475411808bc00a4280b7573b67cf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347556"
---
# <a name="_expand"></a>_expand

Изменяет размер блока памяти.

## <a name="syntax"></a>Синтаксис

```C
void *_expand(
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

**_expand** возвращает пустоту указателя на перераспределенный блок памяти. **_expand,** в отличие от **realloc,** не может переместить блок, чтобы изменить его размер. Таким образом, при наличии достаточной памяти для расширения блока, не перемещая его, параметр *memblock* **_expand** такой же, как и значение возврата.

**_expand** возвращает **NULL,** когда ошибка обнаружена во время его работы. Например, если **_expand** используется для сжатия блока памяти, он может обнаружить повреждения в небольшой куче блока или недействительным блок указателя и вернуть **NULL**.

Если не хватает памяти, чтобы расширить блок до данного размера, не перемещая его, функция возвращает **NULL.** **_expand** никогда не возвращает блок, расширенный до размера меньше, чем просили. Если происходит сбой, **errno** указывает на характер сбоя. Для получения дополнительной информации о **errno**, см [Errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы проверить новый размер товара, используйте **_msize.** Чтобы получить указатель на тип, не **превышающие пустоты,** используйте тип, отлитый на значении возврата.

## <a name="remarks"></a>Remarks

Функция **_expand** изменяет размер ранее выделенного блока памяти, пытаясь расширить или сбить блок без перемещения его местоположения в куче. Параметр *memblock* указывает на начало блока. Параметр *размера* дает новый размер блока, в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным. *memblock* не должен быть блоком, который был освобожден.

> [!NOTE]
> На 64-битных платформах **_expand** может не сокращать блокировку, если новый размер меньше текущего размера; в частности, если блок был меньше 16K в размере и, следовательно, выделены в низкой фрагментации кучи, **_expand** оставляет блок без изменений и возвращает *memblock*.

Когда приложение связано с отладкой версии библиотек исправления C, **_expand** решает [_expand_dbg.](expand-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Эта функция проверяет свои параметры. Если *memblock* является нулевой указатель, эта функция вызывает недействительным обработчик параметров, как описано в [параметрвалиции](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, **errno** устанавливается **в EINVAL** и функция возвращает **NULL**. Если *размер* больше, чем **_HEAP_MAXREQ,** **errno** устанавливается на **ENOMEM** и функция возвращает **NULL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_expand.c

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   char *bufchar;
   printf( "Allocate a 512 element buffer\n" );
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )
      exit( 1 );
   printf( "Allocated %d bytes at %Fp\n",
         _msize( bufchar ), (void *)bufchar );
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )
      printf( "Can't expand" );
   else
      printf( "Expanded block to %d bytes at %Fp\n",
            _msize( bufchar ), (void *)bufchar );
   // Free memory
   free( bufchar );
   exit( 0 );
}
```

```Output
Allocate a 512 element buffer
Allocated 512 bytes at 002C12BC
Expanded block to 1024 bytes at 002C12BC
```

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Бесплатный](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
