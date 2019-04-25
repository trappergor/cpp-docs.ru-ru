---
title: Практическое руководство. Отправлять сообщение через равные промежутки времени
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: 0bf5f93e2a570761874232a88a23289e59e58d94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321966"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Практическое руководство. Отправлять сообщение через равные промежутки времени

В этом примере показано, как использовать параллелизм::[класс timer](../../parallel/concrt/reference/timer-class.md) для отправки сообщения с регулярным интервалом.

## <a name="example"></a>Пример

В следующем примере используется `timer` объекта, чтобы сообщать о ходе выполнения длительной операции. Этот пример содержит ссылки `timer` объект [concurrency::call](../../parallel/concrt/reference/call-class.md) объекта. `call` Объект выводит индикатор хода выполнения на консоль с регулярным интервалом. [Concurrency::Timer:: Start](reference/timer-class.md#start) метод запускает таймер в отдельном контексте. `perform_lengthy_operation` Вызовы функций [concurrency::wait](reference/concurrency-namespace-functions.md#wait) функции в основном контексте для имитации длительной операции.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

В этом примере получается следующий результат:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `report-progress.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**cl.exe /EHsc report-progress.cpp**

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
