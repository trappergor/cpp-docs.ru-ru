---
title: Практическое руководство. Использование класса Context для реализации семафора
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 92f77fade972bff1528bc9a22416670354c70f34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366710"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Практическое руководство. Использование класса Context для реализации семафора

В этом разделе показано, как использовать класс concurrency::Context для реализации класса семафора.

`Context` Класс позволяет блокировать или разрешать текущего контекста выполнения. Блокирование или разрешение текущего контекста полезно при текущем контексте не может продолжаться, поскольку ресурс недоступен. Объект *семафора* является примером ситуации, где текущий контекст выполнения должны ждать освобождения ресурса. Семафор, как и объект критической секции — объект синхронизации, который позволяет коду в одном контексте на монопольный доступ к ресурсу. Тем не менее в отличие от объекта критической секции семафор позволяет более чем один контекст параллельный доступ к ресурсу. Если максимальное число контекстов удерживает блокировку семафора, каждый дополнительный контекст необходимо дождаться снятия блокировки.

### <a name="to-implement-the-semaphore-class"></a>Чтобы реализовать класс semaphore

1. Объявите класс с именем `semaphore`. Добавить `public` и `private` разделы для этого класса.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. В `private` раздел `semaphore` объявите [std::atomic](../../standard-library/atomic-structure.md) переменную, которая содержит счетчик семафора и [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) объект, содержащий контексты что должны ожидать освобождения семафора.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. В `public` раздел `semaphore` , следует реализовать конструктор. Конструктор принимает `long long` значение, указывающее максимальное число контекстов, которые могут одновременно содержать блокировки.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. В `public` раздел `semaphore` , следует реализовать `acquire` метод. Этот метод уменьшает значение счетчика семафора в виде атомарной операции. Если счетчик семафора становится отрицательным, добавьте текущий контекст в конец очереди ожидания и вызовите [Concurrency::Context:: Block](reference/context-class.md#block) метод для блокирования текущего контекста.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. В `public` раздел `semaphore` , следует реализовать `release` метод. Этот метод увеличивает счетчик семафора в виде атомарной операции. Если счетчик семафора является отрицательным, прежде чем операция инкремента, имеется по крайней мере один контекст, ожидающий блокировки. В этом случае Разблокируйте контекст, в начале очереди ожидания.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Пример

`semaphore` В этом примере класс функционирует параллельно, так как `Context::Block` и `Context::Yield` методы уступить выполнение, чтобы среда выполнения может выполнять другие задачи.

`acquire` Метод уменьшает значение счетчика, но он может не завершиться Добавление контекста в очередь ожидания до другой контекст вызовет метод `release` метод. С учетом этого, `release` метод использует цикл управления "Счетчик", который вызывает [Concurrency::Context:: yield](reference/context-class.md#yield) ожидания для метода `acquire` метод, чтобы завершить добавление контекста.

`release` Можно вызвать метод `Context::Unblock` метод до `acquire` вызовы методов `Context::Block` метод. У вас нет для защиты от такого состояния гонки, так как среда выполнения обеспечивает для этих методов, который требуется вызывать в любом порядке. Если `release` вызовы методов `Context::Unblock` перед `acquire` вызовы методов `Context::Block` же контекста, контекст остается незаблокированным. Только среда выполнения требует, что при каждом вызове `Context::Block` сопоставляется с соответствующим вызовом метода `Context::Unblock`.

В следующем примере показан полный `semaphore` класса. `wmain` Функции показано базовое использование этого класса. `wmain` Функция использует [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) алгоритм будет создавать несколько задач, которым требуется доступ к семафору. Так как три потока может быть установлена блокировка в любое время, некоторые задачи необходимо дождаться другой задачи завершить и снятия блокировки.

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

Дополнительные сведения о `concurrent_queue` , представлена в разделе [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md). Дополнительные сведения о `parallel_for` алгоритм, см. в разделе [параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте код примера и вставьте его в проект Visual Studio или вставьте его в файл с именем `cooperative-semaphore.cpp` и выполните следующую команду в окне командной строки Visual Studio.

**/ EHsc CL.exe cooperative-semaphore.cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Можно использовать *Получение ресурса есть инициализация* шаблон (RAII) для ограничения доступа к `semaphore` объект для данной области. В разделе шаблон RAII структуру данных выделена в стеке. Что инициализирует структуры данных, или получает ресурса при его создании и уничтожает или освобождает ресурс, при уничтожении структуре данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из внешней области видимости. Таким образом, ресурс надлежащее управление при возникновении исключения или если функция содержит несколько `return` инструкций.

В следующем примере определяется класс, который называется `scoped_lock`, который определен в `public` раздел `semaphore` класса. `scoped_lock` Класс похож на [Concurrency::critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) и [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) классы. Конструктор `semaphore::scoped_lock` получает доступ к заданной `semaphore` объекта и деструктор освобождает доступ к этому объекту.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
В следующем примере изменяется в теле рабочей функции, передаваемое `parallel_for` алгоритм, что в ней используется RAII для освобождения семафора до выполнения возврата функцией. Такой подход гарантирует, что эта рабочая функция исключений.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>См. также

[Контексты](../../parallel/concrt/contexts.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)
