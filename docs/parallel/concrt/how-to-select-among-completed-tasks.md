---
title: Практическое руководство. Выбор среди завершенных задач
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: 75ecac8dd0e8845401e3e287e8c95ea614055970
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142473"
---
# <a name="how-to-select-among-completed-tasks"></a>Практическое руководство. Выбор среди завершенных задач

В этом примере показано, как использовать классы [Concurrency:: Choice](../../parallel/concrt/reference/choice-class.md) и [Concurrency:: Join](../../parallel/concrt/reference/join-class.md) , чтобы выбрать первую задачу для завершения алгоритма поиска.

## <a name="example"></a>Пример

В следующем примере параллельно выполняются два алгоритма поиска и выбирается первый алгоритм для завершения. В этом примере определяется тип `employee`, содержащий числовой идентификатор и зарплату для сотрудника. Функция `find_employee` находит первого сотрудника с указанным идентификатором или заработной платой. Функция `find_employee` также обрабатывает случай, когда ни один из сотрудников не имеет указанного идентификатора или зарплаты. Функция `wmain` создает массив объектов `employee` и ищет несколько значений идентификатора и оклада.

В примере используется объект `choice` для выбора из следующих вариантов:

1. Сотрудник с указанным идентификатором существует.

1. Сотрудник, имеющий указанную зарплату, существует.

1. Не существует сотрудника с указанным идентификатором или зарплатой.

В первых двух случаях в примере используется объект [Concurrency:: single_assignment](../../parallel/concrt/reference/single-assignment-class.md) для хранения идентификатора и другой объект `single_assignment` для хранения зарплаты. В примере используется объект `join` для третьего случая. Объект `join` состоит из двух дополнительных `single_assignment` объектов: один для случая, когда не существует сотрудника с указанным идентификатором, и один для случая, когда сотрудник с указанной зарплатой не существует. Объект `join` отправляет сообщение, когда каждый из его членов получает сообщение. В этом примере объект `join` отправляет сообщение, когда не существует сотрудника с указанным идентификатором или зарплатой.

В примере используется объект [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) для параллельного выполнения обоих алгоритмов поиска. Каждая задача поиска записывает в один из объектов `single_assignment`, чтобы указать, существует ли данный сотрудник. В примере используется функция [Concurrency:: Receive](reference/concurrency-namespace-functions.md#receive) , чтобы получить индекс первого буфера, содержащего сообщение, и блок `switch` для вывода результата.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

В этом примере формируются следующие данные:

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

В этом примере используется вспомогательная функция [Concurrency:: make_choice](reference/concurrency-namespace-functions.md#make_choice) для создания `choice` объектов и вспомогательная функция [concurrency:: make_join](reference/concurrency-namespace-functions.md#make_join) для создания объектов `join`.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `find-employee.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc ФИНД-емплойи. cpp**

## <a name="see-also"></a>См. также раздел

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Класс choice](../../parallel/concrt/reference/choice-class.md)<br/>
[Класс join](../../parallel/concrt/reference/join-class.md)
