---
title: "_aligned_offset_malloc | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_malloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_aligned_offset_malloc"
  - "aligned_offset_malloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_aligned_offset_malloc - функция"
  - "aligned_offset_malloc - функция"
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_offset_malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет память по определенной границе выравнивания.  
  
## Синтаксис  
  
```  
void * _aligned_offset_malloc(  
   size_t size,   
   size_t alignment,   
   size_t offset  
);  
```  
  
#### Параметры  
 \[входящий\] `size`  
 Размер запрошенного выделения памяти.  
  
 \[входящий\] `alignment`  
 Значение выравнивания, которое должно быть целочисленной степенью двойки.  
  
 \[входящий\] `offset`  
 Смещение в выделении памяти для обеспечения выравнивания.  
  
## Возвращаемое значение  
 Указатель на блок памяти, который был выделен, или `NULL` , если операция завершилась неудачно.  
  
## Заметки  
 `_aligned_offset_malloc` удобна, когда выравнивание необходимо во вложенном элементе; например, если выравнивание было необходимо во вложенном классе.  
  
 `_aligned_offset_malloc` основана на `malloc`; дополнительные сведения см. в разделе [malloc](../../c-runtime-library/reference/malloc.md).  
  
 `_aligned_offset_malloc` помечена `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
 Эта функция устанавливает `errno` в значение `ENOMEM`, выделение памяти завершилось неудачно, или если запрошенный размер был больше `_HEAP_MAXREQ`.  Дополнительные сведения о `errno` см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  Кроме того, `_aligned_offset_malloc` проверяет свои параметры.  Если `alignment` не степень двойки, или если `offset` больше или равно `size` и отлично от нуля, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает `NULL` и устанавливает `errno` в значение `EINVAL`.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_aligned_offset_malloc`|\<malloc.h\>|  
  
## Пример  
 Дополнительные сведения см. в разделе [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)  
  
## См. также  
 [Выравнивание данных](../../c-runtime-library/data-alignment.md)