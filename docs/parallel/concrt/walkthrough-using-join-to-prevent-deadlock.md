---
title: "Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "предотвращение взаимоблокировки объединений [среда выполнения с параллелизмом]"
  - "взаимоблокировка, предотвращение [среда выполнения с параллелизмом]"
  - "нежадные объединения, пример"
  - "класс join, пример"
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе на примере проблемы обедающих философов показано использование класса [concurrency::join](../Topic/join%20Class.md) для исключения взаимоблокировок в приложении.  В программном приложении *взаимоблокировка* возникает, если каждый из двух или более процессов удерживает ресурс и ожидает освобождения какого\-либо другого ресурса другим процессом.  
  
 Проблема обедающих философов является конкретным примером общего ряда проблем, когда несколько параллельных процессов совместно используют один набор ресурсов.  
  
## Обязательные компоненты  
 Прежде чем начать выполнение этого пошагового руководства, необходимо ознакомиться со следующими разделами.  
  
-   [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Пошаговое руководство. Создание приложения на основе агента](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
-   [Структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md)  
  
##  <a name="top"></a> Подразделы  
 Это пошаговое руководство содержит следующие подразделы.  
  
-   [Проблема обедающих философов](#problem)  
  
-   [Упрощенная реализация](#deadlock)  
  
-   [Использование join для предотвращения взаимоблокировок](#solution)  
  
##  <a name="problem"></a> Проблема обедающих философов  
 Проблема обедающих философов позволяет проиллюстрировать создание взаимоблокировки в приложении.  Пять философов сидят за круглым столом.  В определенный момент времени каждый из них может либо размышлять, либо есть.  Каждый философ вынужден делиться лежащими перед ним китайскими палочками для еды: одной палочкой с соседом слева, а другой — с соседом справа.  Расположение палочек на столе показано на следующем рисунке.  
  
 ![Проблема обедающих философов](../../parallel/concrt/media/dining_philosophersproblem.png "Dining\_PhilosophersProblem")  
  
 Для еды каждому философу нужно две палочки.  Если каждый философ держит в руках одну палочку и ждет, пока ему передадут другую, ни один из них не сможет поесть, и все умрут от голода.  
  
 \[[Наверх](#top)\]  
  
##  <a name="deadlock"></a> Упрощенная реализация  
 В следующем примере показана упрощенная реализация проблемы обедающих философов.  Класс `philosopher`, наследуемый от [concurrency::agent](../../parallel/concrt/reference/agent-class.md), позволяет каждому философу действовать независимо.  В этом примере общий массив объектов [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md) используется для предоставления каждому объекту `philosopher` монопольного доступа к паре китайских палочек.  
  
 Для связи реализации с иллюстрацией класс `philosopher` представляет одного философа.  Переменная `int` представляет одну палочку.  Объекты `critical_section` используются в качестве держателей для китайских палочек.  Метод `run` моделирует жизнь философа.  Метод `think` моделирует процесс мышления, а метод `eat` — процесс еды.  
  
 Объект `philosopher` блокирует оба объекта `critical_section`, чтобы смоделировать удаление палочек из держателей до вызова метода `eat`.  После вызова метода `eat` объект `philosopher` возвращает палочки держателям, возвращая объекты `critical_section` в незаблокированное состояние.  
  
 Метод `pickup_chopsticks` показывает, где возможны взаимоблокировки.  Если каждый объект `philosopher` получит доступ к одной из блокировок, ни один из объектов `philosopher` не сможет продолжить работу, так как другая блокировка управляется другим объектом `philosopher`.  
  
## Пример  
  
### Описание  
  
### Код  
 [!CODE [concrt-philosophers-deadlock#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-deadlock#1)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `philosophers-deadlock.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc philosophers\-deadlock.cpp**  
  
 \[[Наверх](#top)\]  
  
##  <a name="solution"></a> Использование join для предотвращения взаимоблокировок  
 В этом разделе показано, как использовать буферы сообщений и функции передачи сообщений для снижения вероятности взаимоблокировки.  
  
 Чтобы связать этот пример с предыдущим, класс `philosopher` заменяет каждый объект `critical_section` объектами [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) и `join`.  Объект `join` выполняет функции арбитра, предоставляющего палочки философу.  
  
 В этом примере используется класс `unbounded_buffer`, поскольку когда целевой объект получает сообщение от объекта `unbounded_buffer`, это сообщение удаляется из очереди сообщений.  Благодаря этому объект `unbounded_buffer`, хранящий сообщение, может показать, что палочка доступна.  Объект `unbounded_buffer`, не содержащий сообщение, указывает, что палочка используется.  
  
 В этом примере используется нежадный объект `join`, поскольку нежадное соединение предоставляет каждому объекту `philosopher` доступ к двум палочкам только в том случае, если оба объекта `unbounded_buffer` содержат сообщение.  Жадное соединение не позволяет предотвратить взаимоблокировку, так как жадное соединение принимает сообщения, как только они становятся доступными.  Если все жадные объекты `join` получают одно из сообщений, но бесконечно ожидают, пока станут доступными другие, создаются взаимоблокировки.  
  
 Дополнительные сведения о жадных и нежадных соединениях и различиях между разными типами буферов сообщений см. в разделе [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md).  
  
#### Как избежать взаимоблокировки в этом примере  
  
1.  Удалите из примера следующий код.  
  
     [!CODE [concrt-philosophers-deadlock#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-deadlock#2)]  
  
2.  Измените тип членов данных `_left` и `_right` класса `philosopher` на `unbounded_buffer`.  
  
     [!CODE [concrt-philosophers-join#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#2)]  
  
3.  Измените конструктор `philosopher` для принятия объектов `unbounded_buffer` в качестве параметров.  
  
     [!CODE [concrt-philosophers-join#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#3)]  
  
4.  Измените метод `pickup_chopsticks`, чтобы использовать нежадный объект `join` для получения сообщений из буферов сообщений для обеих палочек.  
  
     [!CODE [concrt-philosophers-join#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#4)]  
  
5.  Измените метод `putdown_chopsticks` для предоставления доступа к палочкам посредством отправки сообщения в буферы сообщений для обеих палочек.  
  
     [!CODE [concrt-philosophers-join#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#5)]  
  
6.  Измените метод `run`, чтобы он хранил результаты метода `pickup_chopsticks` и передавал эти результаты методу `putdown_chopsticks`.  
  
     [!CODE [concrt-philosophers-join#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#6)]  
  
7.  Измените объявление переменной `chopsticks` в функции `wmain` на массив объектов `unbounded_buffer`, каждый из которых содержит одно сообщение.  
  
     [!CODE [concrt-philosophers-join#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#7)]  
  
## Пример  
  
### Описание  
 Далее представлен полный пример, в котором для снижения вероятности взаимоблокировки используются нежадные объекты `join`.  
  
### Код  
 [!CODE [concrt-philosophers-join#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-philosophers-join#1)]  
  
### Комментарии  
 В результате выполнения примера получается следующий результат:  
  
  **aristotle ate 50 times.**  
**descartes ate 50 times.**  
**hobbes ate 50 times.**  
**socrates ate 50 times.**  
**plato ate 50 times.**   
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `philosophers-join.cpp`, затем выполните в окне командной строки Visual Studio следующую команду.  
  
 **cl.exe \/EHsc philosophers\-join.cpp**  
  
 \[[Наверх](#top)\]  
  
## См. также  
 [Пошаговые руководства по среде выполнения с параллелизмом](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md)