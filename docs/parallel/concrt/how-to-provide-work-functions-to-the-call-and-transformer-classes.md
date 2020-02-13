---
title: Практическое руководство. Предоставление рабочих функций классам call и transformer
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: 4d2b7b3c88b51003a96526ef14d9940a8c26c3b3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142486"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Практическое руководство. Предоставление рабочих функций классам call и transformer

В этом разделе показано несколько способов предоставления рабочих функций классам [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) и [Concurrency:: transformer](../../parallel/concrt/reference/transformer-class.md) .

В первом примере показано, как передать лямбда-выражение в объект `call`. Во втором примере показано, как передать объект функции в объект `call`. В третьем примере показано, как привязать метод класса к `call` объекту.

Для иллюстрации каждый пример в этом разделе использует класс `call`. Пример использования класса `transformer` см. в разделе [как использовать преобразователь в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).

## <a name="example"></a>Пример

В следующем примере показан распространенный способ использования класса `call`. В этом примере лямбда-функция передается в конструктор `call`.

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

В этом примере формируются следующие данные:

```Output
13 squared is 169.
```

## <a name="example"></a>Пример

Следующий пример похож на предыдущий, за исключением того, что он использует класс `call` вместе с объектом функции (функтор).

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example"></a>Пример

Следующий пример похож на предыдущий, за исключением того, что для привязки `call` объекта к методу класса используются функции [std:: bind1st](../../standard-library/functional-functions.md#bind1st) и [std:: mem_fun](../../standard-library/functional-functions.md#mem_fun) .

Используйте этот метод, если необходимо привязать `call` или `transformer` объект к конкретному методу класса, а не к оператору вызова функции, `operator()`.

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

Можно также присвоить результат функции `bind1st` объекту [std:: Function](../../standard-library/function-class.md) или использовать ключевое слово `auto`, как показано в следующем примере.

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `call.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc Call. cpp**

## <a name="see-also"></a>См. также раздел

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Практическое руководство. Использование преобразователя в конвейере данных](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[Класс call](../../parallel/concrt/reference/call-class.md)<br/>
[Класс transformer](../../parallel/concrt/reference/transformer-class.md)
