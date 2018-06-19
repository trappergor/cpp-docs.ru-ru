---
title: Структура RUNTIME_FUNCTION | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c2f28380d4a14cf7617653ede20468c45649a8b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379930"
---
# <a name="struct-runtimefunction"></a>структура RUNTIME_FUNCTION
Обработка исключений, основанных на таблицах требует запись таблицы для всех функций, которые выделяют пространство стека или вызова другой функции (например, неконечные функции). Записи в таблице функций имеет следующий формат:  
  
|||  
|-|-|  
|ULONG|Начальный адрес функции|  
|ULONG|Конечный адрес функции|  
|ULONG|Адрес очистки|  
  
 Структура RUNTIME_FUNCTION должна быть выровнена в памяти DWORD. Все адреса задаются относительно образа, то есть их 32-разрядные смещения относительно стартового адреса образа, который содержит запись в таблице функций. Эти записи отсортированы и помещены в раздел .pdata образа PE32 +. Для динамически создаваемых функций [JIT-компиляторов] среда выполнения поддерживает эти функции необходимо использовать RtlInstallFunctionTableCallback или RtlAddFunctionTable для предоставления этих данных в операционную систему. Невыполнение этого требования приведет к ненадежной обработки исключений и отладки процессов.  
  
## <a name="see-also"></a>См. также  
 [Данные раскрутки для обработки исключений и поддержки отладчика](../build/unwind-data-for-exception-handling-debugger-support.md)