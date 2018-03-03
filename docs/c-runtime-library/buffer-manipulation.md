---
title: "Операции с буфером | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 942d0f881ed6453921f6082024be5247a1bb1b65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="buffer-manipulation"></a>Манипуляция буфером
Используйте эти подпрограммы для побайтной работы с областями памяти.  
  
### <a name="buffer-manipulation-routines"></a>Подпрограммы для операций с буфером  
  
|Подпрограмма|Использовать|  
|-------------|---------|  
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Копирование символов из одного буфера в другой, пока указанный символ или заданное число символов не будут скопированы|  
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|Возвращение указателя к первому вхождению указанного символа в буфере в пределах указанного числа символов|  
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Сравнение указанного количество символов из двух буферов|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Копирование указанного количество символов из одного буфера в другой|  
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Сравнение указанного количества символов из двух буферов без учета регистра|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Копирование указанного количество символов из одного буфера в другой|  
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Использование указанного символа для инициализации указанного числа байтов в буфере|  
|[_swab](../c-runtime-library/reference/swab.md)|Смена байтов данных и сохранение их в указанном расположении|  
  
 При перекрытии исходной и целевой областей только `memmove` гарантированно скопирует полный исходный код правильно.  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)