---
title: "Как: управление экземпляром планировщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2e4916e0f563c4034dc27be1e3d911f42a65319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-manage-a-scheduler-instance"></a>Практическое руководство. Управление экземпляром планировщика
Экземпляры планировщика позволяют связывать конкретные политики планирования с различными видами рабочих нагрузок. В этом разделе содержатся два базовых примера, в которых описывается создание и управление экземпляром планировщика.  
  
 В примерах создаются планировщики, использующие политики планировщика по умолчанию. Пример создания планировщика, который использует пользовательскую политику, см. в разделе [как: укажите конкретные политики планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
### <a name="to-manage-a-scheduler-instance-in-your-application"></a>Управление экземпляром планировщика в приложении  
  
1.  Создание [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) значения объекта, который содержит политику планировщик, который нужно использовать.  
  

2.  Вызовите [Concurrency::CurrentScheduler:: CREATE](reference/currentscheduler-class.md#create) метода или [Concurrency::Scheduler:: CREATE](reference/scheduler-class.md#create) метод для создания экземпляра планировщика.  
  
     Если вы используете `Scheduler::Create` метод, вызовите [Concurrency::Scheduler:: Attach](reference/scheduler-class.md#attach) метод, если необходимо связать планировщик с текущим контекстом.  
  
3.  Вызовите [CreateEvent](http://msdn.microsoft.com/library/windows/desktop/ms682396) функцию, чтобы создать дескриптор объекта несигнальное автоматического сброса событий.  
  
4.  Передает этот дескриптор только что созданный для объекта события [Concurrency::CurrentScheduler::](reference/currentscheduler-class.md#registershutdownevent) метода или [Concurrency::Scheduler:: registershutdownevent](reference/scheduler-class.md#registershutdownevent) метод. Эта строка регистрирует события, задаваемое при уничтожении планировщика.  
  
5.  Выполните задачи, необходимые для планирования текущего планировщика.  
  
6.  Вызовите [concurrency::CurrentScheduler::Detach](reference/currentscheduler-class.md#detach) метод, чтобы отключить текущий планировщик и восстановить предыдущий планировщик в качестве текущего.  
  
     Если вы используете `Scheduler::Create` метод, вызовите [Concurrency::Scheduler:: Release](reference/scheduler-class.md#release) способ уменьшения числа ссылок объекта `Scheduler` объекта.  
  
7.  Передает этот дескриптор события [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032) функции чтобы дождаться завершения работы планировщика.  
  
8.  Вызовите [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211) функцию, чтобы закрыть дескриптор объекта события.  
  
## <a name="example"></a>Пример  
 Следующий код показывает два способа управления экземпляром планировщика. В каждом примере сначала используется планировщик по умолчанию для выполнения задачи, выводящей уникальный идентификатор текущего планировщика. В каждом примере затем использует экземпляр планировщика для выполнения той же задачи еще раз. Наконец в каждом примере восстанавливает планировщик по умолчанию, что и текущий и выполняет задачу еще раз.  
  
 В первом примере используется [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) класса для создания экземпляра планировщика и связывания его с текущим контекстом. Во втором примере [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) классом для выполнения этой задачи. Как правило `CurrentScheduler` класс используется для работы с текущего планировщика. Во втором примере, который использует `Scheduler` класса, полезно, если вы хотите управлять, когда планировщик связан с текущим контекстом, или если вы хотите связать конкретные планировщики с конкретными задачами.  
  
 [!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]  
  
 В этом примере формируются следующие данные:  
  
```Output  
Using CurrentScheduler class...  
 
Current scheduler id: 0  
Creating and attaching scheduler...  
Current scheduler id: 1  
Detaching scheduler...  
Current scheduler id: 0  
 
Using Scheduler class...  
 
Current scheduler id: 0  
Creating scheduler...  
Attaching scheduler...  
Current scheduler id: 2  
Detaching scheduler...  
Current scheduler id: 0  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `scheduler-instance.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc scheduler-instance.cpp**  
  
## <a name="see-also"></a>См. также  
 [Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)   
 [Практическое руководство. Задание определенных политик планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)

