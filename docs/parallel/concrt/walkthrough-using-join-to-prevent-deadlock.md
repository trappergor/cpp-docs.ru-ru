---
title: 'Пошаговое руководство: Использование класса join для предотвращения взаимоблокировок | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5deb501cc05c2a771b6e14d5091b1baa95f2f622
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693351"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки
В этом разделе производит Проблема обедающих философов показано использование [concurrency::join](../../parallel/concrt/reference/join-class.md) для недопущения взаимоблокировок в приложении. В приложении программного обеспечения *взаимоблокировка* возникает, когда два или несколько процессов используют ресурс и одновременно ожидают, пока другой процесс не освободит какой-либо из ресурсов.  
  
 Проблема обедающих философов является конкретным примером общего ряда проблем, которые могут возникнуть при набор ресурсов, являющихся общими для нескольких параллельных процессов.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, ознакомьтесь со следующими разделами:  
  
- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
- [Пошаговое руководство. Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Разделы  
 Это пошаговое руководство содержит следующие разделы:  
  
- [Проблема обедающих философов](#problem)  
  
- [Реализация упрощенного](#deadlock)  
  
- [Использование класса join для предотвращения взаимоблокировки](#solution)  
  
##  <a name="problem"></a> Проблема обедающих философов  
 Проблема обедающих философов показано создание взаимоблокировки в приложении. В эту проблему пять философов сидят за круглым столом. Каждый философу переключается между говорить и еды. Каждый философу должны совместно использовать палочка с соседом слева, а другой — с соседом справа. На следующем рисунке для этой структуры.  
  
 ![Проблема философов обеда](../../parallel/concrt/media/dining_philosophersproblem.png "dining_philosophersproblem")  
  
 Для еды каждому философу нужно две палочек. Если каждый философу содержит только один палочка и ожидает другого, затем можно eat ни и все незадействованным.  
  
 [[В начало](#top)]  
  
##  <a name="deadlock"></a> Реализация упрощенного  
 В следующем примере упрощенная реализация проблемы обедающих философов. `philosopher` Класс, который является производным от [concurrency::agent](../../parallel/concrt/reference/agent-class.md), позволяет каждому философу действовать независимо. В примере общий массив объектов [concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) для предоставления каждому `philosopher` объекта эксклюзивного доступа к паре китайских палочек.  
  
 Для связи реализации с иллюстрацией `philosopher` класс представляет один философу. `int` Переменная представляет палочку. `critical_section` Объектов используются в качестве держателей, для которых палочек. `run` Метод моделирует жизнь философу. `think` Метод моделирует процесс мышления и `eat` — процесс еды.  
  
 Объект `philosopher` блокирует оба `critical_section` объектов, чтобы смоделировать удаление палочек из держателей до вызывает `eat` метод. После вызова `eat`, `philosopher` объект возвращает палочек владельцам, задав `critical_section` объектов обратно в разблокировать состояние.  
  
 `pickup_chopsticks` Метод показывает, где может произойти взаимоблокировка. Если все `philosopher` объект получит доступ к одной блокировки, а затем нет `philosopher` объекта можно продолжить, так как другая блокировка управляется другим `philosopher` объекта.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `philosophers-deadlock.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc philosophers-deadlock.cpp**  
  
 [[В начало](#top)]  
  
##  <a name="solution"></a> Использование класса join для предотвращения взаимоблокировки  
 В этом разделе показано, как использовать буферы сообщений и функции передачи сообщений для снижения вероятности возникновения взаимоблокировки.  
  
 Чтобы связать этот пример и предыдущий, `philosopher` класс заменяет каждый `critical_section` объектов с помощью [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) объекта и `join` объекта. `join` Объект выступает в качестве арбитра, предоставляющего палочек философу.  
  
 В этом примере используется `unbounded_buffer` класса так, как если целевой объект получает сообщение от `unbounded_buffer` объекта, сообщение удаляется из очереди сообщений. Это позволяет `unbounded_buffer` объект, содержащий сообщение, указывающее, что палочка доступна. `unbounded_buffer` Объекта, не содержащий сообщение указывает, что палочка используется.  
  
 В этом примере используется нежадный `join` объекта, так как дает нежадное объединение каждого `philosopher` объекта доступа для обеих палочек только если оба `unbounded_buffer` объекты содержат сообщение. Жадное объединение не могли бы помешать взаимоблокировки, так как жадное объединение принимает сообщения, как только они станут доступны. Взаимоблокировка может произойти, если все жадном `join` объекты получают одно из сообщений, но ждать бесконечно для других станут доступны.  
  
 Дополнительные сведения о соединениях жадного и нежадного и различия между разными типами буферов сообщений см. в разделе [асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
#### <a name="to-prevent-deadlock-in-this-example"></a>Для недопущения взаимоблокировок в этом примере  
  
1.  Удалите следующий код из примера.  
  
 [!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]  
  
2.  Измените тип `_left` и `_right` данные-члены `philosopher` класса `unbounded_buffer`.  
  
 [!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]  
  
3.  Изменить `philosopher` конструктор, чтобы занять `unbounded_buffer` объектов в качестве параметров.  
  
 [!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]  
  
4.  Изменить `pickup_chopsticks` метод, чтобы использовать нежадный `join` объекта для получения сообщений из буферов сообщений для обеих палочек.  
  
 [!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]  
  
5.  Изменить `putdown_chopsticks` метод для предоставления доступа к палочек путем отправки сообщения в буферы сообщений для обеих палочек.  
  
 [!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]  
  
6.  Изменить `run` метод для хранения результатов `pickup_chopsticks` метод и передавать эти результаты `putdown_chopsticks` метод.  
  
 [!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]  
  
7.  Измените объявление `chopsticks` переменных в `wmain` функции как массив из `unbounded_buffer` объектов, каждый из которых содержит одно сообщение.  
  
 [!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Ниже приведен полный пример, использующий нежадном `join` объектов во избежание возникновения взаимоблокировки.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]  
  
### <a name="comments"></a>Комментарии  
 В этом примере формируются следующие данные:  
  
```Output  
aristotle ate 50 times.  
descartes ate 50 times.  
hobbes ate 50 times.  
socrates ate 50 times.  
plato ate 50 times.  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `philosophers-join.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc philosophers-join.cpp**  
  
 [[В начало](#top)]  
  
## <a name="see-also"></a>См. также  
 [Пошаговые руководства для среды выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)
