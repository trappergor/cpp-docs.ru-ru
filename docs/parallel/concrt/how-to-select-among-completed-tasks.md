---
title: Практическое руководство. Выбор среди завершенных задач
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 0d31f9bd16aaa70cc773e60e4f1193e66ec520f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62205646"
---
# <a name="how-to-select-among-completed-tasks"></a>Практическое руководство. Выбор среди завершенных задач

В этом примере показано, как использовать [concurrency::choice](../../parallel/concrt/reference/choice-class.md) и [concurrency::join](../../parallel/concrt/reference/join-class.md) классы, чтобы выбрать первую задачу для завершения алгоритма поиска.

## <a name="example"></a>Пример

В следующем примере выполняются два алгоритма поиска в параллельном режиме и выбирает первый алгоритм для завершения. В этом примере определяется `employee` тип, который содержит числовой идентификатор и зарплату сотрудника. `find_employee` Функция находит первый сотрудник, имеющий указанный идентификатор или зарплату. `find_employee` Функция также обрабатывает, если ни один из сотрудников есть предоставленный идентификатор или заработной платы. `wmain` Функция создает массив `employee` объектов и выполняет поиск нескольких значений идентификатора и зарплаты.

В примере используется `choice` объекта можно выбрать один из следующих случаев:

1. Сотрудник с предоставленным идентификатором существует.

1. Сотрудник, у кого есть зарплату существует.

1. Существует сотрудника с предоставленным идентификатором или заработной платы.

Для первых двух случаях, в примере используется [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) объекта, содержащего идентификатор, а другой `single_assignment` объекта, содержащего заработной платы. В примере используется `join` объекта в третьем случае. `join` Объект состоит из двух дополнительных `single_assignment` объектов, один для сотрудника с предоставленным идентификатором существует и один для сотрудника с зарплату существует. `join` Объект отправляет сообщение, когда каждый из его членов получает сообщение. В этом примере `join` объект отправляет сообщение, если сотрудника с предоставленным идентификатором, или существует заработной платы.

В примере используется [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта для параллельного выполнения обоих алгоритмов поиска. Каждая задача поиска запись в один из `single_assignment` объектов, чтобы указать, существует ли заданный сотрудник. В примере используется [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функцию для получения индекса первого буфера, который содержит сообщение и `switch` блок для вывода результата.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

В этом примере формируются следующие данные:

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

В этом примере используется [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) вспомогательная функция для создания `choice` объектов и [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) вспомогательная функция для создания `join` объектов.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `find-employee.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe find-employee.cpp**

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Класс choice](../../parallel/concrt/reference/choice-class.md)<br/>
[Класс join](../../parallel/concrt/reference/join-class.md)
