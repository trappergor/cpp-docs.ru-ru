---
title: "_matherr | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _matherr
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
- _matherr
- matherr
dev_langs: C++
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c7aa22479630605279b0d1364317d479bd1eac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="matherr"></a>_matherr
Обрабатывает математические ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _matherr(  
   struct _exception *except   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *except*  
 Указатель на структуру, содержащую сведения об ошибке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция _**matherr** возвращает значение 0 в случае ошибки или ненулевое значение в случае успеха. Если \_**matherr** возвращает значение 0, может отобразиться сообщение об ошибке и `errno` будет равно соответствующему значению ошибки. Если \_**matherr** возвращает ненулевое значение, сообщение об ошибке не появляется и `errno` остается неизменным.  
  
 Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция _**matherr** обрабатывает ошибки, создаваемые функциями математических библиотек для чисел с плавающей точкой. Эти функции вызывают \_**matherr** в случае обнаружения ошибки.  
  
 Для специальной обработки ошибок можно задать другое определение _**matherr**. При использовании динамически связанной версии библиотеки времени выполнения языка C (Msvcr90.dll) можно заменить подпрограмму \_**matherr** по умолчанию в исполняемом файле клиента определенной пользователем версией. Однако невозможно заменить подпрограмму `_matherr` по умолчанию в клиенте библиотеки DLL Msvcr90.dll.  
  
 При возникновении ошибки в математической подпрограмме _**matherr** вызывается с указателем на структуру типа **_exception** (указанной в Math.h) в качестве аргумента. Структура **_exception** содержит следующие элементы.  
  
 **int type**  
 Тип исключения.  
  
 **char \*name**  
 Имя функции, в которой возникла ошибка.  
  
 **double arg1**, **arg2**  
 Первый и второй (если есть) аргументы функции.  
  
 **double retval**  
 Значение, возвращаемое функцией.  
  
 **type** определяет тип математической ошибки. Это одно из следующих значений, определенных в Math.h.  
  
 `_DOMAIN`  
 Ошибка домена аргумента.  
  
 `_SING`  
 Сингулярность аргумента.  
  
 `_OVERFLOW`  
 Ошибка переполнения диапазона.  
  
 `_PLOSS`  
 Частичная потеря значимости.  
  
 `_TLOSS`  
 Полная потеря значимости.  
  
 `_UNDERFLOW`  
 Результат слишком мал для представления. (Данное условие в настоящий момент не поддерживается.)  
  
 Элемент структуры**name** является указателем на строку, завершающуюся нуль-символом и содержащую имя функции, которая вызвала ошибку. Элементы структуры **arg1** и **arg2** определяют значения, вызвавшие ошибку. (Если указан только один аргумент, он хранится в **arg1**.)  
  
 Возвращаемое значение по умолчанию для данной ошибки равно **retval**. Если вы измените возвращаемое значение, оно должно определять, действительно ли произошла ошибка.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_matherr`|\<math.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_matherr.c  
/* illustrates writing an error routine for math   
 * functions. The error function must be:  
 *      _matherr  
 */  
  
#include <math.h>  
#include <string.h>  
#include <stdio.h>  
  
int main()  
{  
    /* Do several math operations that cause errors. The _matherr  
     * routine handles _DOMAIN errors, but lets the system handle  
     * other errors normally.  
     */  
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );  
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );  
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );  
}  
  
/* Handle several math errors caused by passing a negative argument  
 * to log or log10 (_DOMAIN errors). When this happens, _matherr  
 * returns the natural or base-10 logarithm of the absolute value  
 * of the argument and suppresses the usual error message.  
 */  
int _matherr( struct _exception *except )  
{  
    /* Handle _DOMAIN errors for log or log10. */  
    if( except->type == _DOMAIN )  
    {  
        if( strcmp( except->name, "log" ) == 0 )  
        {  
            except->retval = log( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
        else if( strcmp( except->name, "log10" ) == 0 )  
        {  
            except->retval = log10( -(except->arg1) );  
            printf( "Special: using absolute value: %s: _DOMAIN "  
                     "error\n", except->name );  
            return 1;  
        }  
    }  
    printf( "Normal: " );  
    return 0;    /* Else use the default actions */  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Special: using absolute value: log: _DOMAIN error  
log( -2.0 ) = 6.931472e-001  
Special: using absolute value: log10: _DOMAIN error  
log10( -5.0 ) = 6.989700e-001  
Normal: log( 0.0 ) = -1.#INF00e+000  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   