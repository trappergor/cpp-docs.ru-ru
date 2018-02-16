---
title: "_gcvt_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _gcvt_s
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
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 567738b488ae648dbd67ea1d2b5cdf34b649170c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="gcvts"></a>_gcvt_s
Преобразует значение с плавающей запятой в строку. Это версия функции [_gcvt](../../c-runtime-library/reference/gcvt.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `buffer`  
 Буфер для сохранения результата преобразования.  
  
 [in] `sizeInBytes`  
 Размер буфера.  
  
 [in] `value`  
 Преобразуемое значение.  
  
 [in] `digits`  
 Количество значащих цифр хранятся.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль при успешном завершении. В случае отказа в связи с недопустимым параметром (см. недопустимые значения в следующей таблице) вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, возвращается код ошибки. Коды ошибок определяются в файле ERRNO.H. Список этих ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Назад|Значение в `buffer`|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|any|any|any|`EINVAL`|Без изменений.|  
|Не `NULL` (указывает на допустимый адрес в памяти)|нуль|any|any|`EINVAL`|Без изменений.|  
|Не `NULL` (указывает на допустимый адрес в памяти)|any|any|>= `sizeInBytes`|`EINVAL`|Без изменений.|  
  
 **Проблемы безопасности**  
  
 Функция `_gcvt_s` может вызвать ошибку нарушения прав доступа, если `buffer` не указывает на допустимый адрес в памяти и не имеет значение `NULL`.  
  
## <a name="remarks"></a>Примечания  
 Функция `_gcvt_s` преобразует значение с плавающей запятой `value` в строку символов (включает знак десятичной запятой и при необходимости байт знака) и сохраняет эту строку в `buffer`. Длина `buffer` должна быть достаточной для хранения преобразованного значения, а также автоматически добавляемого нуль-символа. Буфер длины `_CVTBUFSIZE` достаточен для любого значения с плавающей запятой. Если буфер имеет размер `digits` + 1, функция не перезаписывает конец буфера, поэтому для этой операции необходимо использовать буфер достаточного размера. Функция `_gcvt_s` пытается создать `digits` разрядов в десятичном формате. Если это не удается, создается `digits` разрядов в экспоненциальном формате. Нули в конце могут исключаться из преобразования.  
  
 В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устраняя необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Отладочная версия этой функции сначала заполняет буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<error.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)