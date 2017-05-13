---
title: "div | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- div
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- div
dev_langs:
- C++
helpviewer_keywords:
- div function
- quotients, computing
- quotients
- dividing integers
- remainder computing
ms.assetid: 8ae80d97-54fd-499e-b14c-e30993b58119
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e1e92656713a31d3057dfe180bd1cb4e819ceb5b
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="div"></a>div
Вычисляет частное и остаток от деления двух целочисленных значений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
div_t div(   
   int numer,  
   int denom   
);  
ldiv_t div(  
   long numer,  
   long denom  
); /* C++ only */   
lldiv_t div(  
   long long numer,  
   long long denom  
); /* C++ only */  
```  
  
#### <a name="parameters"></a>Параметры  
 `numer`  
 Числитель.  
  
 `denom`  
 Знаменатель.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `div`, вызванная с использованием аргументов типа `int`, возвращает структуру типа `div_t`, состоящую из частного и остатка. Возвращаемое значение перегруженной функции с аргументами типа `long` — `ldiv_t`. Структуры `div_t` и `ldiv_t` определены в STDLIB.H.  
  
## <a name="remarks"></a>Примечания  
 Функция `div` производит деление `numer` на `denom`, вычисляя таким образом частное и остаток. Структура [div_t](../../c-runtime-library/standard-types.md) содержит частное, `int quot`, и остаток, `int rem`. Знак частного совпадает со знаком математического частного. Его абсолютное значение представляет собой наибольшее целое число, которое меньше абсолютного значения математического частного. Если знаменатель равен 0, выполнение программы прекратится и появится сообщение об ошибке.  
  
 Перегруженные версии, принимающие аргументы типа `long` или `long long`, доступны только для кода C++. Тип возвращаемого значения [ldiv_t](../../c-runtime-library/standard-types.md) содержит элементы `long quot` и `long rem`, а тип возвращаемого значения [lldiv_t](../../c-runtime-library/standard-types.md) содержит элементы `long long quot` и `long long rem`, которые имеют те же смысловые значения, что и члены `div_t`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`div`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_div.c  
// arguments: 876 13  
  
// This example takes two integers as command-line  
// arguments and displays the results of the integer  
// division. This program accepts two arguments on the  
// command line following the program name, then calls  
// div to divide the first argument by the second.  
// Finally, it prints the structure members quot and rem.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <math.h>  
  
int main( int argc, char *argv[] )  
{  
   int x,y;  
   div_t div_result;  
  
   x = atoi( argv[1] );  
   y = atoi( argv[2] );  
  
   printf( "x is %d, y is %d\n", x, y );  
   div_result = div( x, y );  
   printf( "The quotient is %d, and the remainder is %d\n",  
           div_result.quot, div_result.rem );  
}  
```  
  
```Output  
x is 876, y is 13  
The quotient is 67, and the remainder is 5  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [ldiv, lldiv](../../c-runtime-library/reference/ldiv-lldiv.md)   
 [imaxdiv](../../c-runtime-library/reference/imaxdiv.md)
