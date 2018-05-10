---
title: 'Как: использование фильтра блоков сообщений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92de322142e56eb9907da2e19d350c3af9c8a7d9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-a-message-block-filter"></a>Практическое руководство. Использование фильтра блоков сообщений
В этом документе показано, как использовать функцию фильтрации, чтобы позволить блоку асинхронное сообщение для принятия или отклонения сообщения в зависимости от полезных данных сообщения.  
  
 При создании объекта блока сообщений, таких как [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md), [concurrency::call](../../parallel/concrt/reference/call-class.md), или [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md), можно указать *функция filter* , определяет, является ли блок сообщений принимает или отклоняет сообщение. Функция фильтрации является хорошим способом гарантировать, что блок сообщений получать только определенные значения.  
  
 Функции фильтрации важны, так как они позволяют соединять блоки сообщений для создания *сети потока данных*. В сети потока данных блоки сообщений управляют потоком данных, обрабатывая только сообщения, которые соответствуют заданным критериям. Сравним это модель управления потоком, где поток данных контролируется с помощью структур управления, например условных операторов, циклов и так далее.  
  
 Этот документ содержит простой пример использования фильтра сообщений. Дополнительные примеры использования фильтров сообщений и модели потока данных для соединения блоков сообщений см. в разделе [Пошаговое руководство: создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) и [Пошаговое руководство: создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md) .  
  
## <a name="example"></a>Пример  
 Рассмотрим следующую функцию `count_primes`, который иллюстрирует базовое использование блока сообщений, который не выполняет фильтрацию входящих сообщений. Блок сообщений добавляет простые числа к [std::vector](../../standard-library/vector-class.md) объекта. `count_primes` Функция отправляет несколько чисел блоку сообщений, принимает выходные значения от блока сообщений, а также выводит эти простые числа на консоль.  
  
 [!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]  
  
 `transformer` Объект обрабатывает все входные значения; Однако он требует только простые числа. Несмотря на то, что приложение может быть написано, чтобы отправитель сообщений отправлял только простые числа, требования получателя сообщений не всегда известны.  
  
## <a name="example"></a>Пример  
 Следующая функция `count_primes_filter`, выполняет одну и ту же задачу как `count_primes` функции. Тем не менее `transformer` объект в этой версии использует функцию фильтрации на прием только простые числа. Функция, которая выполняет действие, которое принимает только простые числа; Таким образом, он не требуется вызывать `is_prime` функции.  
  
 Поскольку `transformer` объект получает только простые числа `transformer` может сам содержать простые числа. Другими словами `transformer` в этом примере не должен добавлять простые числа к `vector` объекта.  
  
 [!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]  
  
 `transformer` Объект сейчас обрабатывает только простые числа. В предыдущем примере `transformer` объект обрабатывает все сообщения. Таким образом приведенного выше должен получить одинаковое количество сообщений, которые он отправляет. В этом примере используется результат [concurrency::send](reference/concurrency-namespace-functions.md#send) функцию, чтобы определить, сколько сообщений нужно получить от `transformer` объекта. `send` Возврата функцией `true` при буфер сообщений принимает сообщение и `false` при буфер сообщений отклоняет сообщение. Таким образом сколько раз, что буфер сообщений принимает сообщение соответствует количество простых чисел.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример кода. Пример вызывает и `count_primes` функции и `count_primes_filter` функции.  
  
 [!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `primes-filter.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc простые числа filter.cpp**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Функции фильтров может быть лямбда-функции, указателя функции или объекта функции. Любая функция фильтрации принимает одно из следующих форм:  
  
```Output  
bool (T)  
bool (T const &)  
```  
  
 Чтобы избежать ненужных копирования данных, используйте второй формы при наличии Агрегатный тип, который передается по значению.  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Пошаговое руководство: Создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)   
 [Пошаговое руководство: Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)   
 [Класс transformer](../../parallel/concrt/reference/transformer-class.md)
