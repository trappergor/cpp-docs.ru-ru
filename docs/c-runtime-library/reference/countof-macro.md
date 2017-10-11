---
title: "Макрос _countof | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 71d4310525f1d96184749b5b0b24cb0cf1da8512
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="countof-macro"></a>Макрос _countof
Вычисляют количество элементов в статически выделенном массиве.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `array`  
 Имя массива.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Количество элементов в массиве, выраженное как `size_t`.  
  
## <a name="remarks"></a>Примечания  
 Убедитесь, что `array` действительно массив, а не указатель. В C функция `_countof` дает ошибочные результаты, если `array` является указателем. В C++ если параметр `_countof` является указателем, функция `array` не скомпилируется.  
  
## <a name="requirements"></a>Требования  
  
|Макрос|Обязательный заголовок|  
|-----------|---------------------|  
|`_countof`|\<stdlib.h>|  
  
## <a name="example"></a>Пример  
  
```  
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
 [Оператор sizeof](../../cpp/sizeof-operator.md)
