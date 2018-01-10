---
title: "Как: выбор среди завершенных задач | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cce496f205052bdb6986abc0cee158622e93545
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-select-among-completed-tasks"></a>Практическое руководство. Выбор среди завершенных задач
В этом примере показано, как использовать [concurrency::choice](../../parallel/concrt/reference/choice-class.md) и [concurrency::join](../../parallel/concrt/reference/join-class.md) классов, чтобы выбрать первую задачу для завершения алгоритма поиска.  
  
## <a name="example"></a>Пример  
 В следующем примере параллельно выполняются два алгоритма поиска и выбирает первый алгоритм для выполнения. В этом примере определяется `employee` тип, который содержит числовой идентификатор и зарплату сотрудника. `find_employee` Функция находит первого сотрудника с предоставленным идентификатором или зарплату. `find_employee` Функция также обрабатывает случай, у которых нет сотрудников предоставленным идентификатором или зарплатой. `wmain` Функция создает массив `employee` объекты и выполняет поиск нескольких значений идентификатора и зарплаты.  
  
 В этом примере `choice` объектов для выбора одного из следующих случаев:  
  
1.  Сотрудник с предоставленным идентификатором существует.  
  
2.  Сотрудник с предоставленной зарплатой существует.  
  
3.  Существует сотрудника с предоставленным идентификатором или зарплатой.  
  
 Для первых двух вариантов в этом примере [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) объекта, содержащего идентификатор, а другой `single_assignment` объекта, содержащего зарплаты. В этом примере `join` объекта для третьего случая. `join` Объекта состоит из двух дополнительных `single_assignment` объектов, один для случая, когда существует сотрудника с предоставленным идентификатором и один для сотрудника с предоставленной зарплатой существует. `join` Объект отправляет сообщение, когда каждый из его членов получает сообщение. В этом примере `join` объект отправляет сообщение, если сотрудника с предоставленным идентификатором или существует заработной платы.  
  
 В этом примере [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) объекта для параллельного выполнения обоих алгоритмов поиска. Каждая задача поиска записывает данные в один из `single_assignment` объектов, чтобы указать, существует ли заданный сотрудник. В этом примере [concurrency::receive](reference/concurrency-namespace-functions.md#receive) функции для получения индекса первого буфера, который содержит сообщение и `switch` блок для вывода результата.  
  
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
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `find-employee.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc find-employee.cpp**  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Класс Choice](../../parallel/concrt/reference/choice-class.md)   
 [Класс join](../../parallel/concrt/reference/join-class.md)
