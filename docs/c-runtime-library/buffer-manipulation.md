---
title: Операции с буфером | Документы Майкрософт
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.memory
dev_langs:
- C++
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7544dfa80ce0c7481846383dd812ce30b78290
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389092"
---
# <a name="buffer-manipulation"></a>Операции с буфером

Используйте эти подпрограммы для побайтной работы с областями памяти.

## <a name="buffer-manipulation-routines"></a>Подпрограммы для операций с буфером

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

При перекрытии исходной и целевой областей только **memmove** гарантированно скопирует полный исходный код правильно.

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)
