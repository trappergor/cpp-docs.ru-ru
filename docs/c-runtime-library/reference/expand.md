---
title: _expand
ms.date: 11/04/2016
api_name:
- _expand
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
ms.openlocfilehash: cb986d893bd862e61ae595317a890fb489c19919
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941558"
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

*size*<br/>
Новый размер в байтах.

## <a name="return-value"></a>Возвращаемое значение

**_expand** возвращает указатель void на перераспределенный блок памяти. **_expand**, в отличие от **перераспределения**, не может переместить блок, чтобы изменить его размер. Таким образом, если достаточно памяти для расширения блока без его перемещения, параметр *мемблокк* в **_expand** будет таким же, как и возвращаемое значение.

**_expand** возвращает **значение NULL** , если во время выполнения операции обнаружена ошибка. Например, если **_expand** используется для сжатия блока памяти, он может обнаружить повреждение в небольшой куче блоков или недопустимый указатель на блок и вернуть **значение NULL**.

Если недостаточно памяти для расширения блока до заданного размера без перемещения, функция возвращает **значение NULL**. **_expand** никогда не возвращает блок, развернутый до размера, меньшего запрошенного. В случае сбоя значение « **No** » указывает на природу сбоя. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr".

Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы проверить новый размер элемента, используйте **_msize**. Чтобы получить указатель на тип, отличный от **void**, используйте приведение типа к возвращаемому значению.

## <a name="remarks"></a>Примечания

Функция **_expand** изменяет размер выделенного ранее блока памяти, пытаясь развернуть или Свернуть блок, не перемещая его расположение в куче. Параметр *мемблокк* указывает на начало блока. Параметр *size* задает новый размер блока в байтах. Содержимое блока в пределах наименьшего из нового и старого размеров остается неизменным. *мемблокк* не должен быть освобожденным блоком.

> [!NOTE]
> На 64-разрядных платформах **_expand** может не проконтрактировать блок, если новый размер меньше текущего размера. в частности, если размер блока был менее 16 КБ и, следовательно, выделен в куче с низкой фрагментацией, **_expand** оставляет блок без изменений и возвращает *мемблокк*.

Если приложение связано с отладочной версией библиотек времени выполнения C, **_expand** разрешается в [_expand_dbg](expand-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Эта функция проверяет свои параметры. Если *мемблокк* является пустым указателем, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а функция возвращает **значение NULL**. Если *Размер* больше, чем **_HEAP_MAXREQ**, то для свойства "значение **" возвращается значение** **еномем** , а функция возвращает **null**.

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
