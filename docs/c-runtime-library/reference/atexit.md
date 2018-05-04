---
title: atexit | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- atexit
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
- atexit
dev_langs:
- C++
helpviewer_keywords:
- processing, at exit
- atexit function
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d66954348d5d812fac7eca0b231304267cc26157
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atexit"></a>atexit

Обрабатывает указанную функцию на выходе.

## <a name="syntax"></a>Синтаксис

```C
int atexit(
   void (__cdecl *func )( void )
);
```

### <a name="parameters"></a>Параметры

*func*<br/>
Функция, которую требуется вызвать.

## <a name="return-value"></a>Возвращаемое значение

**atexit** возвращает 0 в случае успеха или ненулевое значение, если произошла ошибка.

## <a name="remarks"></a>Примечания

**Atexit** функции передается адрес функции *func* вызывается при завершении программы в обычном режиме. Последующие вызовы **atexit** создают регистр функций, которые выполняются в порядке следования последним поступил — первым обслужен (LIFO). Передаваемые в функции **atexit** не могут принимать параметры. **atexit** и **_onexit** используется для хранения регистр функций кучи. В связи с этим количество функций, которое можно зарегистрировать, ограничивается только памятью кучи.

Код в **atexit** функция не должна содержать все зависимости от любой библиотеки DLL, которая может уже были выгружены при **atexit** функция.

Для создания ANSI-совместимые приложения, используется стандарт ANSI **atexit** функции (а не как **_onexit** функции).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**atexit**|\<stdlib.h>|

## <a name="example"></a>Пример

Это отправлений четыре функции программы в стек функции, выполняемый при **atexit** вызывается. При завершении работы программы эти программы выполняются в обратном порядке.

```C
// crt_atexit.c
#include <stdlib.h>
#include <stdio.h>

void fn1( void ), fn2( void ), fn3( void ), fn4( void );

int main( void )
{
   atexit( fn1 );
   atexit( fn2 );
   atexit( fn3 );
   atexit( fn4 );
   printf( "This is executed first.\n" );
}

void fn1()
{
   printf( "next.\n" );
}

void fn2()
{
   printf( "executed " );
}

void fn3()
{
   printf( "is " );
}

void fn4()
{
   printf( "This " );
}
```

```Output
This is executed first.
This is executed next.
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
