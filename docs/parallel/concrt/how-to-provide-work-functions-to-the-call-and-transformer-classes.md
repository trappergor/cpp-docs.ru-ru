---
title: Практическое руководство. Предоставление рабочих функций классам call и transformer
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: c41c29dae277105f268171503e662e2a02e3857e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205794"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Практическое руководство. Предоставление рабочих функций классам call и transformer

В этом разделе приводится несколько способов предоставления рабочих функций [concurrency::call](../../parallel/concrt/reference/call-class.md) и [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) классы.

Первый пример показывает способ передачи лямбда-выражения `call` объекта. Во втором примере показано, как передать объект функции в `call` объекта. Третий пример показано, как привязать метод класса для `call` объекта.

Для иллюстрации каждого примера в этом разделе использует `call` класса. Пример, использующий `transformer` , представлена в разделе [как: Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example"></a>Пример

В следующем примере показано обычный способ использования `call` класса. В этом примере передается лямбда-функцию для `call` конструктор.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

В этом примере формируются следующие данные:

```Output
13 squared is 169.
```

## <a name="example"></a>Пример

Следующий пример похож на предыдущий, за исключением того, что она использует `call` вместе с объектом функции (функтор).

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>Пример

Следующий пример похож на предыдущий, за исключением того, что она использует [std::bind1st](../../standard-library/functional-functions.md#bind1st) и [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) функции для привязки `call` , методу класса.

Используйте этот метод, если требуется привязать `call` или `transformer` , определенный класс методу, а не оператор вызова функции `operator()`.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Вы также можете назначить результат `bind1st` функцию [std::function](../../standard-library/function-class.md) или `auto` ключевое слово, как показано в следующем примере.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `call.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**CL.exe call.cpp/EHsc**

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[Класс call](../../parallel/concrt/reference/call-class.md)<br/>
[Класс transformer](../../parallel/concrt/reference/transformer-class.md)
