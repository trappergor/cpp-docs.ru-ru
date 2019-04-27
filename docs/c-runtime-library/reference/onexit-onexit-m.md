---
title: _onexit, _onexit_m
ms.date: 11/04/2016
apiname:
- _onexit
- _onexit_m
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
- _onexit
- onexit_m
- onexit
- _onexit_m
helpviewer_keywords:
- onexit function
- registry, registering exit routines
- _onexit_m function
- onexit_m function
- _onexit function
- registering exit routines
- registering to be called on exit
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
ms.openlocfilehash: c190f777032904802f771bab9fc323ba305ff32e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156049"
---
# <a name="onexit-onexitm"></a>_onexit, _onexit_m

Регистрирует подпрограмму, вызываемую во время выхода.

## <a name="syntax"></a>Синтаксис

```C
_onexit_t _onexit(
   _onexit_t function
);
_onexit_t_m _onexit_m(
   _onexit_t_m function
);
```

### <a name="parameters"></a>Параметры

*function*<br/>
Указатель на функцию, которая должна вызываться при выходе.

## <a name="return-value"></a>Возвращаемое значение

**_onexit** возвращает указатель на функцию, в случае успеха или **NULL** Если нет места для хранения указателя на функцию.

## <a name="remarks"></a>Примечания

**_Onexit** функции передается адрес функции (*функция*) вызывается при нормальном завершении программы. Последовательные вызовы **_onexit** создают регистр функций, которые выполняются в порядке LIFO (последним in-first-out). Передаваемые в функции **_onexit** не могут принимать параметры.

В случае, когда **_onexit** вызывается из библиотеки DLL, подпрограммы, зарегистрированные с помощью **_onexit** выгрузке после выполнения для библиотеки DLL **DllMain** вызывается с DLL_PROCESS_DETACH.

**_onexit** является расширением Майкрософт. Чтобы обеспечить переносимость ANSI, используйте функцию [atexit](atexit.md). **_Onexit_m** версия функции для использования смешанного режима.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_onexit**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_onexit.c

#include <stdlib.h>
#include <stdio.h>

/* Prototypes */
int fn1(void), fn2(void), fn3(void), fn4 (void);

int main( void )
{
   _onexit( fn1 );
   _onexit( fn2 );
   _onexit( fn3 );
   _onexit( fn4 );
   printf( "This is executed first.\n" );
}

int fn1()
{
   printf( "next.\n" );
   return 0;
}

int fn2()
{
   printf( "executed " );
   return 0;
}

int fn3()
{
   printf( "is " );
   return 0;
}

int fn4()
{
   printf( "This " );
   return 0;
}
```

### <a name="output"></a>Вывод

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[atexit](atexit.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[__dllonexit](../../c-runtime-library/dllonexit.md)<br/>
