---
title: "_fcvt | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9f191d64115bca85502d8fd3fbe0525c0e2be65c
ms.lasthandoff: 02/24/2017

---
# <a name="fcvt"></a>_fcvt
Преобразует число с плавающей запятой в строку. Существует более безопасная версия этой функции, см. раздел [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
char *_fcvt(   
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
 Число разрядов после десятичной запятой.  
  
 `dec`  
 Указатель на сохраненную позицию десятичной запятой.  
  
 `sign`  
 Указатель на сохраненный индикатор знака.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `_fcvt` возвращает указатель на строку разрядов или NULL, если возникает ошибка.  
  
## <a name="remarks"></a>Примечания  
 Функция `_fcvt` преобразует число с плавающей запятой в строку, завершаемую нуль-символом. Параметр `value` представляет собой преобразуемое число с плавающей запятой. Функция `_fcvt` сохраняет цифры параметра `value` в виде строки и добавляет нуль-символ ("\0"). Параметр `count` определяет количество цифр, сохраняемых после десятичной запятой. Избыточные цифры округляются до `count` знаков. Если количество цифр меньше точности `count`, строка дополняется нулями.  
  
 Общее количество разрядов, возвращаемое `_fcvt`, не должно превышать `_CVTBUFSIZE`.  
  
 В строке сохраняются только цифры. Положение десятичной запятой и знак `value` можно получить из параметров `dec` и sign после вызова. Параметр `dec` указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр `sign` указывает на целое число, обозначающее знак величины `value`. Целое число имеет значение 0, если значение `value` положительное, и ненулевое значение, если значение `value` отрицательное.  
  
 Различие между функциями `_ecvt` и `_fcvt` заключается в интерпретации параметра `count`. Функция `_ecvt` интерпретирует параметр `count` как общее число цифр в выходной строке, а функция `_fcvt` интерпретирует параметр `count` как количество цифр после десятичной запятой.  
  
 `_ecvt` и `_fcvt` используют для преобразования один статически выделенный буфер. Каждый вызов одной из этих подпрограмм уничтожает результат предыдущего вызова.  
  
 Эта функция проверяет свои параметры. Если `dec` или `sign` имеют значение NULL или `count` равен нулю, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, для `errno` задается значение `EINVAL` и возвращается значение NULL.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
