---
title: "Как: использование класса Context для реализации семафора | Документы Microsoft"
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
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03884d69877053976fdaf04e507c4c1c4214026e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ
В этом разделе показано, как использовать класс concurrency::Context для реализации класса семафора.  
  
 `Context` Класс позволяет блокировать или разрешать текущий контекст выполнения. Блокирование или разрешение текущего контекста полезно при текущем контексте невозможно продолжить, так как ресурс недоступен. Объект *семафора* примером может служить ситуация, когда текущему контексту выполнения приходится ждать освобождения ресурса. Семафор, как и объект критической секции — объект синхронизации, позволяющий коду из одного контекста на монопольный доступ к ресурсу. Однако в отличие от объекта критической секции семафор позволяет более одного контекста параллельный доступ к ресурсу. Если максимальное число контекстов удерживает блокировку семафора, каждый дополнительный контекст должен ожидать снятия блокировки.  
  
### <a name="to-implement-the-semaphore-class"></a>Чтобы реализовать класс semaphore  
  
1.  Объявите класс с именем `semaphore`. Добавить `public` и `private` разделы к этому классу.  
  
 [!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]  
  
2.  В `private` раздел `semaphore` объявите [std::atomic](../../standard-library/atomic-structure.md) переменную, которая содержит счетчик семафора и [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) объект, содержащий контексты что должны ожидать освобождения семафора.  
  
 [!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]  
  
3.  В `public` раздел `semaphore` класса, реализуйте конструктор. Конструктор принимает `long long` значение, указывающее максимальное число контекстов, одновременно может быть установлена блокировка.  
  
 [!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]  

4.  В `public` раздел `semaphore` , следует реализовать `acquire` метод. Этот метод уменьшает значение счетчика семафора в виде атомарной операции. Если значение счетчика семафора становится отрицательным, добавьте текущий контекст в конец очереди ожидания и вызовите [Concurrency::Context:: Block](reference/context-class.md#block) метод для блокирования текущего контекста.  
  
 [!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]  
  
5.  В `public` раздел `semaphore` , следует реализовать `release` метод. Этот метод увеличивает счетчик семафора виде атомарной операции. Если значение счетчика семафора отрицательное до операции инкремента, имеется хотя бы один контекст, ожидающий блокировки. В этом случае Разблокируйте контекст, в начале очереди ожидания.  
  
 [!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]  
  
## <a name="example"></a>Пример  
 `semaphore` Класс в этом примере функционирует параллельно, так как `Context::Block` и `Context::Yield` методы передают выполнение, чтобы среда выполнения может выполнять другие задачи.  
  
 `acquire` Метод уменьшает значение счетчика, но он может не завершиться Добавление контекста в очередь ожидания до другой контекст вызовет метод `release` метод. С учетом этого, `release` метод использует цикл управления "Счетчик", который вызывает [Concurrency::Context:: yield](reference/context-class.md#yield) метод для ожидания `acquire` метод, чтобы завершить добавление контекста.  
  
 `release` Можно вызвать метод `Context::Unblock` метод перед `acquire` вызовы метода `Context::Block` метод. Необходимо защититься от такого состояния гонки, так как среда выполнения позволяет эти методы будут вызываться в любом порядке. Если `release` вызовы метода `Context::Unblock` перед `acquire` вызовы метода `Context::Block` для того же контекста, контекст остается незаблокированным. Среда выполнения требует только что при каждом вызове функции `Context::Block` сопоставляется с соответствующим вызовом `Context::Unblock`.  
  
 В следующем примере показано полное `semaphore` класса. `wmain` Функции показано базовое использование этого класса. `wmain` Функция использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм создаст несколько задач, которым требуется доступ к семафора. Так как три потока может быть установлена блокировка в любое время, некоторые задачи, необходимо дождаться другой задачи для завершения и отмены блокировки.  
  
 [!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]  
  
 В этом примере получается следующий результат.  
  
```Output  
In loop iteration 5...  
In loop iteration 0...  
In loop iteration 6...  
In loop iteration 1...  
In loop iteration 2...  
In loop iteration 7...  
In loop iteration 3...  
In loop iteration 8...  
In loop iteration 9...  
In loop iteration 4...  
```  
  
 Дополнительные сведения о `concurrent_queue` см. в описании [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md). Дополнительные сведения о `parallel_for` алгоритм, в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `cooperative-semaphore.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc совместной semaphore.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Можно использовать *Получение ресурса есть инициализация* шаблон (RAII) для ограничения доступа к `semaphore` объект для данной области. При использовании шаблона RAII структура данных выделяется в стеке. Что структуры данных инициализирует или приобретает ресурс, когда он создается и уничтожает или освобождает ресурс, при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Таким образом, ресурс эффективно управляется при возникновении исключения или если функция содержит несколько `return` инструкции.  
  
 В следующем примере определяется класс с именем `scoped_lock`, которая определена в `public` раздел `semaphore` класса. `scoped_lock` Похож [Concurrency::critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) и [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) классы. Конструктор `semaphore::scoped_lock` класс получает доступ к данной `semaphore` объекта, а деструктор предоставляет доступ к этому объекту.  
  
 [!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]    
 В следующем примере изменяется в теле рабочей функции, передаваемое `parallel_for` алгоритм, что он использует шаблон RAII для освобождения семафора до выполнения возврата функцией. Этот способ обеспечивает рабочую функцию исключений.  
  
 [!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Контексты](../../parallel/concrt/contexts.md)   
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

