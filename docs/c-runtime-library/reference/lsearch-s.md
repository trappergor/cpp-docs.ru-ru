---
title: "_lsearch_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _lsearch_s
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
- _lsearch_s
- lsearch_s
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a680c990ec91edf225057ea729fd3343a57610d4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="lsearchs"></a>_lsearch_s
Выполняет линейный поиск значения. Версия функции [_lsearch](../../c-runtime-library/reference/lsearch.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало массива, где будет производиться поиск.  
  
 `num`  
 Число элементов.  
  
 `size`  
 Размер каждого элемента в байтах.  
  
 `compare`  
 Указатель на подпрограмму сравнения. Второй параметр — это указатель на ключ для поиска. Третий параметр — это указатель на элемент массива, который будет сравниваться с ключом.  
  
 `context`  
 Указатель на объект, доступ к которому может получить функция сравнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Если ключ `key` найден, `_lsearch_s` возвращает указатель на элемент массива `base`, соответствующий `key`. Если ключ `key` не найден, `_lsearch_s` возвращает указатель на вновь добавленный в конец массива элемент.  
  
 Если функции переданы недопустимые параметры, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, параметр `errno` устанавливается в значение `EINVAL`, и функция возвращает `NULL`. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Условия ошибок  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|!= 0|any|`EINVAL`|  
|any|any|any|any|нуль|`EINVAL`|  
|any|any|`NULL`|любой|любые|`EINVAL`|  
  
## <a name="remarks"></a>Примечания  
 Функция `_lsearch_s` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width` каждый. В отличие от функции `bsearch_s`, `_lsearch_s` не требует, чтобы массив был отсортирован. Если `key` не найден, `_lsearch_s` добавляет его в конец массива и увеличивает `num` на единицу.  
  
 Функция `compare` представляет собой указатель на предоставляемую пользователем подпрограмму, которая сравнивает два элемента массива и возвращает значение, показывающее, как соотносятся их значения. Функция `compare` также принимает указатель на контекст в качестве первого аргумента. Функция `_lsearch_s` вызывает функцию `compare` один или несколько раз во время поиска, передавая при каждом вызове указатели на два элемента массива. Функция `compare` должна сравнивать элементы и возвращать либо отличное от нуля значение (если элементы различаются), либо 0 (если элементы идентичны).  
  
 Указатель `context` может быть полезен, если структура данных, в которой производится поиск, является частью объекта и функции `compare` требуется доступ к членам объекта. Например, код в функции `compare` может привести указатель void к соответствующему типу объекта и получить доступ к членам этого объекта. Добавление указателя `context` делает `_lsearch_s` более безопасной, поскольку наличие дополнительного контекста может использоваться для предотвращения ошибок повторного входа, вязанных с использованием статических переменных для предоставления функции `compare` доступа к данным.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_lsearch_s`|\<search.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Поиск и сортировка](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)