---
title: Макрос _countof
ms.date: 03/22/2018
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
- _countof
- countof
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
ms.openlocfilehash: 3debd63da7d218e29f31847034c69d89b4691643
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942688"
---
# <a name="_countof-macro"></a>Макрос _countof

Выполняет вычисление количества элементов в статическом массиве.

## <a name="syntax"></a>Синтаксис

```C
#define _countof(array) (sizeof(array) / sizeof(array[0]))
```

### <a name="parameters"></a>Параметры

*array*<br/>
Имя массива.

## <a name="return-value"></a>Возвращаемое значение

Число элементов в массиве, выраженное в виде **size_t**.

## <a name="remarks"></a>Примечания

**_countof** реализуется как макрос препроцессора, аналогичный функции. В C++ версии имеется дополнительный механизм шаблонов для обнаружения во время компиляции, если вместо статического объявленного массива передается указатель.

Убедитесь, что *массив* фактически является массивом, а не указателем. В языке C **_countof** выдает ошибочные результаты, если *массив* является указателем. В C++ **_countof** не удается скомпилировать, если *массив* является указателем.  Массив, переданный в качестве параметра функции *декайс в указатель*, что означает, что внутри функции нельзя использовать **_countof** для определения экстента массива.

## <a name="requirements"></a>Требования

|Макрос|Обязательный заголовок|
|-----------|---------------------|
|**_countof**|\<stdlib.h>|

## <a name="example"></a>Пример

```cpp
// crt_countof.cpp
#define _UNICODE
#include <stdio.h>
#include <stdlib.h>
#include <tchar.h>

int main( void )
{
   _TCHAR arr[20], *p;
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );
   // In C++, the following line would generate a compile-time error:
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)

   _tcscpy_s( arr, _countof(arr), _T("a string") );
   // unlike sizeof, _countof works here for both narrow- and wide-character strings
}
```

```Output
sizeof(arr) = 40 bytes
_countof(arr) = 20 elements
```

## <a name="see-also"></a>См. также

[Оператор sizeof](../../cpp/sizeof-operator.md)<br/>
