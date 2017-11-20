---
title: "_fcvt_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs: C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 922fed9dde6e3f38ae1276034ce84a97db9f99be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fcvts"></a>_fcvt_s
Преобразует число с плавающей запятой в строку. Это версия функции [_fcvt](../../c-runtime-library/reference/fcvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Предоставленный буфер, в который помещается результат преобразования.  
  
 [in] `sizeInBytes`  
 Размер буфера в байтах.  
  
 [in] `value`  
 Число, которое требуется преобразовать.  
  
 [in] `count`  
 Число разрядов после десятичной запятой.  
  
 [выходной] `dec`  
 Указатель на сохраненную позицию десятичной запятой.  
  
 [выходной] `sign`  
 Указатель на сохраненный индикатор знака.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае сбоя возвращаемое значение представляет собой код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 В случае недопустимого параметра, как указано в приведенной ниже таблице, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает для `errno` значение `EINVAL` и возвращает `EINVAL`.  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`sizeInBytes`|значение|count|dec|sign|Return|Значение в `buffer`|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|любые|любые|любые|любые|любые|`EINVAL`|Без изменений.|  
|Не `NULL` (указывает на допустимую память)|<=0|any|любые|любые|любые|`EINVAL`|Не изменено.|  
|any|любые|любые|любые|`NULL`|любые|`EINVAL`|Не изменено.|  
|any|любые|любые|любые|любые|`NULL`|`EINVAL`|Без изменений.|  
  
 **Проблемы безопасности**  
  
 Функция `_fcvt_s` может вызвать ошибку нарушения прав доступа, если `buffer` не указывает на допустимый адрес в памяти и не имеет значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_fcvt_s` преобразует число с плавающей запятой в строку, завершаемую нуль-символом. Параметр `value` представляет собой преобразуемое число с плавающей запятой. Функция `_fcvt_s` сохраняет цифры параметра `value` в виде строки и добавляет нуль-символ ("\0"). Параметр `count` определяет количество цифр, сохраняемых после десятичной запятой. Избыточные цифры округляются до `count` знаков. Если количество цифр меньше точности `count`, строка дополняется нулями.  
  
 В строке сохраняются только цифры. Положение десятичной запятой и знак `value` можно получить из параметров `dec` и `sign` после вызова. Параметр `dec` указывает на целочисленное значение; это целочисленное значение представляет положение десятичной запятой относительно начала строки. Ноль или отрицательное целое число означают, что десятичная запятая располагается слева от первой цифры. Параметр `sign` указывает на целое число, обозначающее знак величины `value`. Целое число имеет значение 0, если значение `value` положительное, и ненулевое значение, если значение `value` отрицательное.  
  
 Буфер длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой.  
  
 Различие между функциями `_ecvt_s` и `_fcvt_s` заключается в интерпретации параметра `count`. `_ecvt_s`интерпретирует `count` как общее число цифр в выходной строке и `_fcvt_s` интерпретирует `count` как количество цифр после десятичной запятой.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочная версия этой функции сначала заполняет буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательный заголовок|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
 **Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)