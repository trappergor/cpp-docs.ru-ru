---
title: "_ecvt | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
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
ms.openlocfilehash: c3992066b5b305a7b9de6ef47c6ba42e15da2518
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="ecvt"></a>_ecvt
Преобразует число `double` в строку. Существует более безопасная версия этой функции, см. раздел [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `value`  
 Число, которое требуется преобразовать.  
  
 `count`  
 Сохраненное число разрядов.  
  
 `dec`  
 Сохраненная позиция десятичной запятой.  
  
 `sign`  
 Знак преобразованного числа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_ecvt` возвращает указатель на строку разрядов или ноль, если возникает ошибка.  
  
## <a name="remarks"></a>Примечания  
 Функция `_ecvt` преобразует число с плавающей запятой в строку символов. Параметр `value` представляет собой преобразуемое число с плавающей запятой. Эта функция сохраняет до `count` разрядов параметра `value` в виде строки и добавляет нуль-символ ("\0"). Если количество разрядов в `value` превышает `count`, младший разряд округляется. Если количество разрядов меньше `count`, строка дополняется нулями.  
  
 Общее количество разрядов, возвращаемое `_ecvt`, не должно превышать `_CVTBUFSIZE`.  
  
 В строке сохраняются только цифры. Положение десятичной запятой и знак `value` можно получить из параметров `dec` и `sign` после вызова. Параметр `dec` указывает на целочисленное значение, отражающее положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр `sign` указывает на целое число, определяющее знак преобразуемого числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.  
  
 Различие между функциями `_ecvt` и `_fcvt` заключается в интерпретации параметра `count`. Функция `_ecvt` интерпретирует параметр `count` как общее число цифр в выходной строке, а функция `_fcvt` интерпретирует параметр `count` как количество цифр после десятичной запятой.  
  
 `_ecvt` и `_fcvt` используют для преобразования один статически выделенный буфер. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.  
  
 Эта функция проверяет свои параметры. Если `dec` или `sign` имеют значение NULL или `count` равен нулю, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, для `errno` задается значение `EINVAL` и возвращается значение NULL.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
