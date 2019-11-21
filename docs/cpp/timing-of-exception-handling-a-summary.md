---
title: 'Timing of exception handling: A summary'
ms.date: 05/07/2019
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 870606c3661df3654581760214e48ef2bdfb1987
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246337"
---
# <a name="timing-of-exception-handling-a-summary"></a>Timing of exception handling: A summary

A termination handler is executed no matter how the **__try** statement block is terminated. Causes include jumping out of the **__try** block, a `longjmp` statement that transfers control out of the block, and unwinding the stack due to exception handling.

> [!NOTE]
>  The Microsoft C++ compiler supports two forms of the `setjmp` and `longjmp` statements. Быстрая версия обходит обработку завершения, однако является более эффективной. To use this version, include the file \<setjmp.h>. Другая версия поддерживает обработку завершения, как описано в предыдущем абзаце. To use this version, include the file \<setjmpex.h>. Увеличение производительности быстрой версии зависит от конфигурации оборудования.

Операционная система выполняет все обработчики завершения в нужном порядке, прежде чем сможет быть выполнен какой-либо другой код, включая тело обработчика исключений.

Если причина прерывания — исключение, система должна сначала выполнить фильтровую часть одного или нескольких обработчиков исключений, а потом определять объект завершения. Используется следующий порядок событий:

1. Выдается исключение.

1. Система анализирует иерархию активных обработчиков исключений и выполняет фильтр обработчика с наивысшим приоритетом; это обработчик исключений, который был установлен последним и имеет наиболее глубокую структуру с точки зрения блоков и вызовов функций.

1. Если этот фильтр передает контроль (возвращает 0), процесс продолжается до тех пор, пока не будет найден фильтр, который не передает контроль.

1. If this filter returns -1, execution continues where the exception was raised, and no termination takes place.

1. Если фильтр возвращает 1, возникают следующие события:

   - Система освобождает стек, снимает все кадры стека между текущим исполняемым кодом (где было создано исключение) и кадром стека, который содержит получающий контроль обработчик исключений.

   - По мере освобождения стека выполняется каждый обработчик завершения в стеке.

   - Выполняется сам обработчик исключений.

   - Контроль переходит к строке кода после окончания этого обработчика исключений.

## <a name="see-also"></a>См. также

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)