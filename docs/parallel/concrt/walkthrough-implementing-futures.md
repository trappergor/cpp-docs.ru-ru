---
title: "Пошаговое руководство. Реализация фьючерсов | Microsoft Docs"
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
  - "реализация фьючерсов [среда выполнения с параллелизмом]"
  - "фьючерсы, реализация [среда выполнения с параллелизмом]"
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# Пошаговое руководство. Реализация фьючерсов
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе показано, как реализовывать futures в приложении. Разделе показано, как объединить существующие функциональные возможности среды выполнения с параллелизмом в нечто дополнительных.  
  
> [!IMPORTANT]
>  В этом разделе рассматривается понятие фьючерсов для демонстрационных целей. Мы рекомендуем использовать [std::future](../../standard-library/future-class.md) или [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) Если требуется асинхронная задача, которая вычисляет значение для последующего использования.  
  
 A *задачи* является вычисление, которое можно разложить на дополнительные, более мелкие вычисления. A *будущих* — это асинхронная задача, которая вычисляет значение для последующего использования.  
  
 Для реализации фьючерсов в этом разделе определяется `async_future` класса.  `async_future` Эти компоненты среды выполнения с параллелизмом использует класс: [concurrency::task_group](../Topic/task_group%20Class.md) класса и [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) класса.  `async_future` Класс использует `task_group` класса для асинхронного вычисления значения и `single_assignment` класса для хранения результата вычисления. Конструктор `async_future` класса принимает рабочую функцию, которая вычисляет результат, и `get` метод извлекает результат.  
  
### <a name="to-implement-the-asyncfuture-class"></a>Реализация класса async_future  
  
1.  Объявите шаблонный класс с именем `async_future` параметризованный по типу результирующего вычисления. Добавление `public` и `private` разделы к этому классу.  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_1.cpp)]  
  
2.  В `private` разделе `async_future` объявите `task_group` и `single_assignment` элемента данных.  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_2.cpp)]  
  
3.  В `public` разделе `async_future` класса, реализуйте конструктор. Конструктор — это шаблон, параметризованный по рабочей функции, вычисляющей результат. Конструктор асинхронно выполняет рабочую функцию в `task_group` данных и использует [concurrency::send](../Topic/send%20Function.md) функции для записи результата в `single_assignment` элемент данных.  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_3.cpp)]  
  
4.  В `public` разделе `async_future` следует реализовать деструктор. Деструктор ожидает завершения выполнения задачи.  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_4.cpp)]  
  
5.  В `public` разделе `async_future` следует реализовать `get` метод. Этот метод использует [concurrency::receive](../Topic/receive%20Function.md) функции для извлечения результата рабочей функции.  
  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере показано полное `async_future` класс и пример его использования.  `wmain` Функция создает std::[вектор](vector%20Class.md) объект, содержащий 10000 случайных целых чисел. Затем он использует `async_future` объектов найти наименьшее и наибольшее значения, содержащиеся в `vector` объекта.  
  
### <a name="code"></a>Код  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>Комментарии  
 В этом примере выводятся следующие данные:  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 В примере используется `async_future::get` метод для извлечения результатов вычисления.  `async_future::get` Метод ожидает завершения, если вычисление еще выполняется вычисления.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Для расширения `async_future` класса обрабатывал исключения, вызываемые рабочей функцией, измените `async_future::get` метод для вызова [Concurrency::task_group:: wait](../Topic/task_group::wait%20Method.md) метод.  `task_group::wait` Метод создает все исключения, возникшие в рабочей функции.  
  
 В следующем примере показано измененная версия `async_future` класса.  `wmain` Функция использует `try`-`catch` блока для печати результата `async_future` объекта или для печати значения исключение, которое создается в рабочей функции.  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_7.cpp)]  
  
 В этом примере выводятся следующие данные:  
  
```Output  
caught exception: error  
```  
  
 Дополнительные сведения о модели обработки исключений в среде выполнения с параллелизмом см. в разделе [Обработка исключений](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio и вставьте его в файл с именем `futures.cpp` и затем выполните следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc futures.cpp**  
  
## <a name="see-also"></a>См. также раздел  
 [Примеры выполнения параллелизма](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [Обработка исключений](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [Класс task_group](../Topic/task_group%20Class.md)   
 [Класс single_assignment](../../parallel/concrt/reference/single-assignment-class.md)
