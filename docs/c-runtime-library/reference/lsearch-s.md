---
title: "_lsearch_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_lsearch_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_lsearch_s"
  - "lsearch_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lsearch_s - функция"
  - "массивы [CRT], поиск"
  - "ключи, поиск в массивах"
  - "линейный поиск"
  - "lsearch_s - функция"
  - "поиск, линейные"
  - "значения, поиск"
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lsearch_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет линейный поиск значения.  Это версия [\_lsearch](../../c-runtime-library/reference/lsearch.md) с усовершенствованиями безопасности, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
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
  
#### Параметры  
 `key`  
 Искомый объект.  
  
 `base`  
 Указатель на начало массива для поиска.  
  
 `num`  
 Количество элементов.  
  
 `size`  
 Размер каждого элемента в байтах.  
  
 `compare`  
 Указатель на процедуру сравнения.  Второй параметр — указатель на ключ для поиска.  Третий параметр — указатель на элемент массива, который будет сравниваться с ключом.  
  
 `context`  
 Указатель на объект, доступ к которому можно получить в функции сравнения.  
  
## Возвращаемое значение  
 Если ключ `key` найден, `_lsearch_s` возвращает указатель на элемент массива `base`, соответствующий `key`.  Если ключ `key` не найден, `_lsearch_s` возвращает указатель на вновь добавленный в конец массива элемент.  
  
 Если функции переданы недопустимые параметры, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция устанавливает `errno` в `EINVAL` и возвращает `NULL`.  Дополнительные сведения см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
### Условия возникновения ошибки  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|any|any|any|any|`EINVAL`|  
|any|`NULL`|any|\!\= 0|any|`EINVAL`|  
|any|any|any|any|нуль|`EINVAL`|  
|any|any|`NULL`|any|any|`EINVAL`|  
  
## Заметки  
 Функция `_lsearch_s` выполняет линейный поиск значения `key` в массиве из `num` элементов шириной `width`.  В отличие от `bsearch_s`, `_lsearch_s` не требует сортированный массив.  Если `key` не найден, `_lsearch_s` добавляет его в конец массива и увеличивает `num`.  
  
 Функция `compare` является указателем на пользовательскую процедуру, которая сравнивает два элемента массива и возвращает значение, которое показывает, как соотносятся их значения.  Функция `compare` также принимает указатель на контекст в качестве первого аргумента.  `_lsearch_s` вызывает процедуру `compare` один или несколько раз во время поиска, передавая указатели на два элемента массива при каждом вызове:  `compare` должна сравнивать элементы и возвращать или отличное от нуля значение \(то есть элементы различаются\), или 0 \(если элементы совпадают\).  
  
 Указатель `context` может быть полезен, если искомая структура данных является частью объекта и функции `compare` требуется доступ к членам объекта.  Например, код в функции `compare` может привести указатель к соответствующему типу объекта и получить доступ к членам этого объекта.  Добавление указателя `context` делает `_lsearch_s` более безопасной, поскольку наличие дополнительного контекста может использоваться для предотвращения ошибок повторного входа, связанных с использованием статических переменных, чтобы сделать данные доступными для функции `compare`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_lsearch_s`|\<search.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Сортировка и поиск](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch\_s](../../c-runtime-library/reference/bsearch-s.md)   
 [\_lfind\_s](../Topic/_lfind_s.md)   
 [\_lsearch](../../c-runtime-library/reference/lsearch.md)