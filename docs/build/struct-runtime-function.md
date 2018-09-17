---
title: Структура RUNTIME_FUNCTION | Документация Майкрософт
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
ms.openlocfilehash: 7f3831dc36664c556cf0a020ed87c60200443fd3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718241"
---
# <a name="struct-runtimefunction"></a>структура RUNTIME_FUNCTION

Обработка исключений на основе таблицы требуется запись таблицы для всех функций, которые выделяют пространство стека или вызова другой функции (например, функции неконечным). Функция записи таблицы имеют формат:

|||
|-|-|
|ULONG|Начальный адрес функции|
|ULONG|Конечный адрес функции|
|ULONG|Адрес очистки|

Структура RUNTIME_FUNCTION должна быть DWORD выравнивания в памяти. Все адреса задаются относительно образа, то есть они являются 32-разрядные смещения от начальный адрес образа, который содержит запись в таблице функций. Эти записи отсортированы и помещены в раздел .pdata образа PE32 +. Для динамически создаваемых функций [JIT-компиляторов] среда выполнения для поддержки этих функций необходимо использовать RtlInstallFunctionTableCallback или RtlAddFunctionTable для предоставления этих сведений в операционную систему. Невыполнение этого требования приведет к ненадежной обработки исключений и отладки процессов.

## <a name="see-also"></a>См. также

[Данные раскрутки для обработки исключений и поддержки отладчика](../build/unwind-data-for-exception-handling-debugger-support.md)