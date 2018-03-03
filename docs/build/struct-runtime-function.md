---
title: "Структура RUNTIME_FUNCTION | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c05dcd516af5c078b4e4e664bae16f65370ca117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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