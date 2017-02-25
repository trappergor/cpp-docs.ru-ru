---
title: "Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "реализация семафора, поддерживающего совместный доступ"
  - "context - класс"
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе показано, как использовать класс concurrency::Context для реализации класса семафора.  
  
  `Context` Класс позволяет блокировать или разрешать текущий контекст выполнения. Блокирование или разрешение текущего контекста полезно, когда текущий контекст не может продолжаться, поскольку ресурс недоступен. A *семафора* приведен пример ситуации, когда текущему контексту выполнения приходится ждать освобождения ресурса. Семафор, как и объект критической секции — объект синхронизации, позволяющий коду из одного контекста осуществлять монопольный доступ к ресурсу. Тем не менее в отличие от объекта критической секции семафор позволяет осуществлять более одного контекста параллельный доступ к ресурсу. Если максимальное число контекстов удерживает блокировку семафора, каждый последующий контекст должен ожидать снятия блокировки.  
  
### <a name="to-implement-the-semaphore-class"></a>Для реализации класса семафора  
  
1.  Объявите класс с именем `semaphore`. Добавление `public` и `private` разделы к этому классу.  
  
 [!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]  
  
2.  В `private` разделе `semaphore` объявите [std::atomic](../../standard-library/atomic-structure.md) переменную, содержащую счетчик семафора и [concurrency::concurrent_queue](../Topic/concurrent_queue%20Class.md) объект, содержащий контексты, которые должны ожидать освобождения семафора.  
  
 [!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]  
  
3.  В `public` разделе `semaphore` класса, реализуйте конструктор. Конструктор принимает `long long` значение, указывающее максимальное число контекстов, которые могут одновременно содержать блокировки.  
  
 [!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]  
  
4.  В `public` разделе `semaphore` следует реализовать `acquire` метод. Этот метод уменьшает значение счетчика семафора в результате атомарной операции. Если значение счетчика семафора становится отрицательным, добавьте текущий контекст в конец очереди ожидания и вызовите [Concurrency::Context:: Block](../Topic/Context::Block%20Method.md) метод для блокирования текущего контекста.  
  
 [!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]  
  
5.  В `public` разделе `semaphore` следует реализовать `release` метод. Этот метод увеличивает счетчик семафора виде атомарной операции. Если значение счетчика семафора отрицательное до начала операции увеличения, существует по крайней мере один контекст, ожидающий блокировки. В этом случае Разблокируйте контекст в начале очереди ожидания.  
  
 [!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]  
  
## <a name="example"></a>Пример  
  `semaphore` Класс в этом примере функционирует параллельно, так как `Context::Block` и `Context::Yield` методы передают выполнение, чтобы среда выполнения может выполнять другие задачи.  
  
  `acquire` Уменьшает значение счетчика, но не может завершить добавление контекста в очередь ожидания до другой контекст вызовет метод `release` метод. С учетом этого, `release` метод использует цикл счетчик, который вызывает [Concurrency::Context:: yield](../Topic/Context::Yield%20Method.md) ожидания для метода `acquire` завершения добавления контекста методом.  
  
  `release` Можно вызвать метод `Context::Unblock` метод до `acquire` вызовы метода `Context::Block` метод. Необходимо защититься от такого состояния гонки, так как среда выполнения позволяет эти методы будут вызываться в любом порядке. Если `release` вызовы метода `Context::Unblock` перед `acquire` вызовы метода `Context::Block` для того же контекста, контекст остается незаблокированным. Среда выполнения требует только что каждый вызов метода `Context::Block` сопоставляется с соответствующим вызовом метода `Context::Unblock`.  
  
 В следующем примере показано полное `semaphore` класса.  `wmain` Функция показывает базовое использование этого класса.  `wmain` Функция использует [concurrency::parallel_for](../Topic/parallel_for%20Function.md) алгоритма, чтобы создать несколько задач, которым необходим доступ к семафору. Так как три потока может быть установлена блокировка в любое время, некоторые задачи, необходимо дождаться другой задачи для завершения и снятия блокировки.  
  
 [!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]  
  
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
  
 Дополнительные сведения о `concurrent_queue` см. в разделе [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md). Дополнительные сведения о `parallel_for` алгоритм, в разделе [Параллельные алгоритмы](../Topic/Parallel%20Algorithms.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio и вставьте его в файл с именем `cooperative-semaphore.cpp` и затем выполните следующую команду в окне командной строки Visual Studio.  
  
 **/ EHsc CL.exe совместной semaphore.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Можно использовать *Получение ресурса есть инициализация* шаблон (RAII), чтобы ограничить доступ к `semaphore` объект для данной области. При использовании шаблона RAII структура данных выделяется в стеке. Что структура данных инициализирует или приобретает ресурс, когда он создается и уничтожает или освобождает ресурс при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Следовательно, ресурс эффективно управляется при возникновении исключения или если функция содержит несколько `return` инструкции.  
  
 В следующем примере определяется класс с именем `scoped_lock`, которая определена в `public` части `semaphore` класса.  `scoped_lock` Напоминает класс [Concurrency::critical_section:: scoped_lock](../Topic/critical_section::scoped_lock%20Class.md) и [Concurrency::reader_writer_lock:: scoped_lock](../Topic/reader_writer_lock::scoped_lock%20Class.md) классы. Конструктор `semaphore::scoped_lock` класс получает доступ к данной `semaphore` объекта, а деструктор предоставляет доступ к этому объекту.  
  
 [!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]  
  
 В следующем примере изменяется тело рабочей функции, который передается `parallel_for` алгоритма, чтобы он использовал шаблон RAII для освобождения семафора до возвращения функции. Этот метод обеспечивает рабочую функцию исключений.  
  
 [!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/CPP/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Контексты](../../parallel/concrt/contexts.md)   
 [Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)

