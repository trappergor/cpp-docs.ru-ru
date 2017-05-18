---
title: "_ecvt_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
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
ms.openlocfilehash: 81bcb9fe1306f5affa49672269890d6f5888a3ac
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="ecvts"></a>_ecvt_s
Преобразует число `double` в строку. Это — версия функции [_ecvt](../../c-runtime-library/reference/ecvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `_Buffer`  
 Заполняется указателем на строку разрядов, результат преобразования.  
  
 [in] `_SizeInBytes`  
 Размер буфера в байтах.  
  
 [in] `_Value`  
 Число, которое требуется преобразовать.  
  
 [in] `_Count`  
 Сохраненное число разрядов.  
  
 [выходной] `_Dec`  
 Сохраненная позиция десятичной запятой.  
  
 [выходной] `_Sign`  
 Знак преобразованного числа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|Возвращаемое значение|Значение в `buffer`|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|любые|любые|любые|любые|любые|`EINVAL`|Без изменений.|  
|Не `NULL` (указывает на допустимую память)|<=0|any|любые|любые|любые|`EINVAL`|Не изменено.|  
|any|любые|любые|любые|`NULL`|любые|`EINVAL`|Не изменено.|  
|any|любые|любые|любые|любые|`NULL`|`EINVAL`|Без изменений.|  
  
 **Проблемы безопасности**  
  
 Функция `_ecvt_s` может вызвать ошибку нарушения прав доступа, если `buffer` не указывает на допустимый адрес в памяти и не имеет значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_ecvt_s` преобразует число с плавающей запятой в строку символов. Параметр `_Value` представляет собой преобразуемое число с плавающей запятой. Эта функция сохраняет до `count` разрядов параметра `_Value` в виде строки и добавляет нуль-символ ("\0"). Если количество разрядов в `_Value` превышает `_Count`, младший разряд округляется. Если количество разрядов меньше `count`, строка дополняется нулями.  
  
 В строке сохраняются только цифры. Положение десятичной запятой и знак `_Value` можно получить из параметров `_Dec` и `_Sign` после вызова. Параметр `_Dec` указывает на целочисленное значение, отражающее положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр `_Sign` указывает на целое число, определяющее знак преобразуемого числа. Если целочисленное значение равно 0, число является положительным. В противном случае число будет отрицательным.  
  
 Буфер длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой.  
  
 Различие между функциями `_ecvt_s` и `_fcvt_s` заключается в интерпретации параметра `_Count`. Функция `_ecvt_s` интерпретирует параметр `_Count` как общее число цифр в выходной строке, а функция `_fcvt_s` интерпретирует параметр `_Count` как количество цифр после десятичной запятой.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочная версия этой функции сначала заполняет буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)
