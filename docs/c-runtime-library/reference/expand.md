---
title: _expand
ms.date: 11/04/2016
apiname:
- _expand
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
ms.openlocfilehash: c1606bedbb1264bddb7674c829fe456f506d6584
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665664"
---
# <a name="expand"></a>_expand

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

*size*<br/>
Новый размер в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_expand** возвращает указатель void на перераспределенный блок памяти. **_expand**, в отличие от **realloc**, не может перемещать блок, чтобы изменить его размер. Таким образом, если имеется достаточный объем памяти, чтобы увеличить блок без его перемещения, *memblock* параметр **_expand** совпадает со значением возвращаемое значение.

**_expand** возвращает **NULL** при обнаружении ошибки во время его работы. Например если **_expand** — используется, чтобы сжать блок памяти, она может обнаружить повреждение в куче с малыми блоками или недопустимый указатель блока и вернуть **NULL**.

Если недостаточно памяти для увеличения блока до заданного размера без его перемещения, функция возвращает **NULL**. **_expand** никогда не возвращает блок, развернутом до размера, меньше запрошенного. Если происходит сбой, **errno** указывает характер ошибки. Дополнительные сведения о **errno**, см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы проверить новый размер элемента, используйте **_msize**. Чтобы получить указатель на тип, отличное от **void**, используйте приведение типов для возвращаемого значения.

## <a name="remarks"></a>Примечания

**_Expand** функция изменяет размер блока ранее выделенной памяти, пытаясь увеличить или уменьшить блок без его перемещения в куче. *Memblock* параметр указывает на начало блока. *Размер* параметр указывает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным. *memblock* не следует блок, который освобожден.

> [!NOTE]
> На 64-разрядных платформах **_expand** не может изменить блок, если новый размер меньше, чем текущий размер; в частности, если блок был меньше 16 КБ и таким образом, выделенных в куче низкой фрагментации, **_expand**  оставляет блок без изменений и возвращает *memblock*.

Когда приложение связано с отладочной версией библиотек времени выполнения языка C, **_expand** разрешается [_expand_dbg](expand-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Эта функция проверяет свои параметры. Если *memblock* является пустым указателем, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **NULL**. Если *размер* больше, чем **_HEAP_MAXREQ**, **errno** присваивается **ENOMEM** и функция возвращает **NULL**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|---------------------|
|**_expand**|\<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[_msize](msize.md)<br/>
[realloc](realloc.md)<br/>
