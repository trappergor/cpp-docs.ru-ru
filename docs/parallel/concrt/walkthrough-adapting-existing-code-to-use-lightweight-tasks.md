---
title: "Пошаговое руководство: Адаптация существующего кода для использования упрощенных задач | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a50ad04421d7b4bcdc4a2c98de8f5a57b255c75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>Пошаговое руководство. Адаптация существующего кода для использования упрощенных задач
В этом разделе показано, как адаптировать имеющийся код, который использует Windows API для создания и выполнения потока, в котором используется упрощенная задача.  
  
 Объект *упрощенной задачи* — это задача, планируемая непосредственно из [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) или [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) объекта. Упрощенные задачи полезны при адаптации существующего кода к использованию функциональных возможностей планирования среды выполнения с параллелизмом.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Перед выполнением этого пошагового руководства, следует ознакомиться с разделом [планировщик](../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем примере показано типичное использование API Windows для создания и выполнения потока. В этом примере используется [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) функции, вызываемой `MyThreadFunction` в отдельном потоке.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]  
  
### <a name="comments"></a>Комментарии  
 В этом примере формируются следующие данные:  
  
```Output  
Parameters = 50, 100  
```  
  
 Ниже показано, как адаптировать в примере кода для использования среды выполнения с параллелизмом для выполнения этой задачи.  
  
### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>Чтобы адаптировать этот пример для использования упрощенных задач  
  
1.  Добавить `#include` директив для файла заголовка concrt.h.  
  
 [!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]  
  
2.  Добавить `using` директивы `concurrency` пространства имен.  
  
 [!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]  
  
3.  Измените объявление `MyThreadFunction` использовать `__cdecl` соглашение о вызовах и возврата `void`.  
  
 [!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]  
  
4.  Изменить `MyData` структуры для включения [concurrency::event](../../parallel/concrt/reference/event-class.md) , сообщающий главному приложению, что задача завершена.  
  
 [!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]  
  
5.  Замените вызов `CreateThread` вызовом [Concurrency::CurrentScheduler:: ScheduleTask](reference/currentscheduler-class.md#scheduletask) метод.  

  
 [!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]  
  

6.  Замените вызов `WaitForSingleObject` вызовом [Concurrency::Event:: wait](reference/event-class.md#wait) метод для ожидания завершения задачи.  

 [!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]  
  
7.  Удалите вызов `CloseHandle`.  
  
8.  Изменить подпись определение `MyThreadFunction` в соответствии с шагом 3.  
  
 [!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]  
  
9. В конце `MyThreadFunction` вызовите метод [Concurrency::Event:: set](reference/event-class.md#set) метод, чтобы сообщить главному приложению, что задача завершена.  
  
 [!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]  
  
10. Удалить `return` инструкции от `MyThreadFunction`.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 В следующем полном примере показан код, который использует упрощенную задачу для вызова `MyThreadFunction` функции.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]  
  
### <a name="comments"></a>Комментарии  
  
## <a name="see-also"></a>См. также  
 [Планировщик задач](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Класс Scheduler](../../parallel/concrt/reference/scheduler-class.md)
