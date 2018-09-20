---
title: 'Практическое: отправлять сообщение через равные промежутки времени | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3c476d9cf633ce9b676dc8f658c94bd0b240461
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384303"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Практическое руководство. Отправка сообщений через определенные интервалы

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

**/ EHsc CL.exe report-progress.cpp**

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
