---
title: Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ
ms.date: 11/04/2016
helpviewer_keywords:
- cooperative semaphore implementing
- context class
ms.assetid: 22f4b9c0-ca22-4a68-90ba-39e99ea76696
ms.openlocfilehash: 5075052592993f413290242e70206b1e227064aa
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141907"
---
# <a name="how-to-use-the-context-class-to-implement-a-cooperative-semaphore"></a>Практическое руководство. Использование класса Context для реализации семафора, поддерживающего параллельный доступ

В этом разделе показано, как использовать класс Concurrency:: Context для реализации класса семафора с совместным использованием.

## <a name="remarks"></a>Remarks

Класс `Context` позволяет блокировать или выдавать текущий контекст выполнения. Блокировка или выработка текущего контекста полезна, если текущий контекст не может быть продолжен, так как ресурс недоступен. *Семафор* — это пример одной ситуации, в которой текущий контекст выполнения должен ждать, пока ресурс станет доступным. Семафор, как и объект критической секции, является объектом синхронизации, который позволяет коду в одном контексте иметь монопольный доступ к ресурсу. Однако, в отличие от объекта критической секции, семафор позволяет параллельно обращаться к ресурсу более чем в одном контексте. Если максимальное число контекстов содержит блокировку семафора, каждый дополнительный контекст должен ожидать освобождения блокировки другим контекстом.

### <a name="to-implement-the-semaphore-class"></a>Реализация класса семафора

1. Объявите класс с именем `semaphore`. Добавьте `public` и `private` разделы в этот класс.

[!code-cpp[concrt-cooperative-semaphore#1](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_1.cpp)]

1. В разделе `private` класса `semaphore` объявите переменную [std:: Atomic](../../standard-library/atomic-structure.md) , которая содержит количество семафоров и объект [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) , содержащий контексты, которые должны ожидать получения семафора.

[!code-cpp[concrt-cooperative-semaphore#2](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_2.cpp)]

1. В разделе `public` класса `semaphore` реализуйте конструктор. Конструктор принимает `long long` значение, указывающее максимальное количество контекстов, которые могут одновременно удерживать блокировку.

[!code-cpp[concrt-cooperative-semaphore#3](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_3.cpp)]

1. В разделе `public` класса `semaphore` реализуйте метод `acquire`. Этот метод уменьшает число семафоров как атомарную операцию. Если число семафоров станет отрицательным, добавьте текущий контекст в конец очереди ожидания и вызовите метод [Concurrency:: Context:: Block](reference/context-class.md#block) , чтобы заблокировать текущий контекст.

[!code-cpp[concrt-cooperative-semaphore#4](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_4.cpp)]

1. В разделе `public` класса `semaphore` реализуйте метод `release`. Этот метод увеличивает число семафоров в виде атомарной операции. Если число семафоров отрицательно до операции приращения, то существует по крайней мере один контекст, ожидающий блокировки. В этом случае Разблокируйте контекст, находящиеся в начале очереди ожидания.

[!code-cpp[concrt-cooperative-semaphore#5](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_5.cpp)]

## <a name="example"></a>Пример

Класс `semaphore` в этом примере выполняется совместно, так как методы `Context::Block` и `Context::Yield` возвращают выполнение, чтобы среда выполнения могла выполнять другие задачи.

Метод `acquire` уменьшает счетчик, но может не завершить добавление контекста в очередь ожидания, прежде чем другой контекст вызовет метод `release`. Для этого метод `release` использует цикл Spin, который вызывает метод [Concurrency:: Context:: Yield](reference/context-class.md#yield) для ожидания завершения добавления контекста методом `acquire`.

Метод `release` может вызвать метод `Context::Unblock`, прежде чем метод `acquire` вызовет метод `Context::Block`. Не требуется защищаться от этого состояния гонки, так как среда выполнения позволяет вызывать эти методы в любом порядке. Если метод `release` вызывает `Context::Unblock` перед тем, как метод `acquire` вызовет `Context::Block` для того же контекста, этот контекст остается незаблокированным. Среда выполнения требует, чтобы каждый вызов `Context::Block` совпадал с соответствующим вызовом `Context::Unblock`.

В следующем примере показан полный класс `semaphore`. Функция `wmain` показывает базовое использование этого класса. Функция `wmain` использует алгоритм [параллелизма::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) , чтобы создать несколько задач, которым требуется доступ к семафору. Так как три потока могут удерживать блокировку в любое время, некоторые задачи должны дожидаться завершения другой задачи и освобождения блокировки.

[!code-cpp[concrt-cooperative-semaphore#6](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_6.cpp)]

В этом примере выводится следующий пример выходных данных.

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

Дополнительные сведения о классе `concurrent_queue` см. в разделе [Parallel Containers and Objects](../../parallel/concrt/parallel-containers-and-objects.md). Дополнительные сведения о алгоритме `parallel_for` см. в разделе [Параллельные алгоритмы](../../parallel/concrt/parallel-algorithms.md).

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `cooperative-semaphore.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc куперативе-семафоре. cpp**

## <a name="robust-programming"></a>Отказоустойчивость

Можно использовать шаблон " *получение ресурсов — инициализация* " (RAII), чтобы ограничить доступ к объекту `semaphore` в данной области. В шаблоне RAII структура данных выделяется в стеке. Эта структура данных Инициализирует или получает ресурс при его создании, а также уничтожает или освобождает этот ресурс при уничтожении структуры данных. Шаблон RAII гарантирует, что деструктор вызывается до выхода из охватывающей области. Таким образом, ресурс правильно управляется при возникновении исключения или если функция содержит несколько `return` инструкций.

В следующем примере определяется класс с именем `scoped_lock`, который определен в разделе `public` класса `semaphore`. Класс `scoped_lock` похож на классы [Concurrency:: critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) и [concurrency:: reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) . Конструктор класса `semaphore::scoped_lock` получает доступ к заданному `semaphore` объекту, и деструктор освобождает доступ к этому объекту.

[!code-cpp[concrt-cooperative-semaphore#7](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_7.cpp)]
В следующем примере изменяется текст рабочей функции, которая передается в алгоритм `parallel_for`, чтобы он использовал RAII, чтобы убедиться, что семафор освобожден до возвращения функции. Этот метод гарантирует, что Рабочая функция будет защищена от исключений.

[!code-cpp[concrt-cooperative-semaphore#8](../../parallel/concrt/codesnippet/cpp/how-to-use-the-context-class-to-implement-a-cooperative-semaphore_8.cpp)]

## <a name="see-also"></a>См. также раздел

[Контексты](../../parallel/concrt/contexts.md)<br/>
[Параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md)
