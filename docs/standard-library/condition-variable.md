---
title: "&lt;condition_variable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<condition_variable>"
dev_langs: 
  - "C++"
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;condition_variable&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет классы [condition\_variable](../standard-library/condition-variable-class.md) и [condition\_variable\_any](../standard-library/condition-variable-any-class.md), которые используются для создания объектов, ожидающие условие для освобождения true.  
  
 Этот заголовок используется среда выполнения с параллелизмом \(ConcRT\), чтобы можно было использовать его вместе с другими механизмами ConcRT.  Дополнительные сведения о ConcRT см. в разделе [Среда выполнения с параллелизмом](../parallel/concrt/concurrency-runtime.md).  
  
## Синтаксис  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  В коде, компилироваться с помощью **\/clr** или **\/clr:pure**, этот заголовок блокируется.  
  
### Примечания  
 Код, который ожидает переменную условия также должен использовать `mutex`.  Вызывающий поток должен блокировать `mutex` до его вызывает функции, ожидающие переменную условия.  `mutex` затем блокировано, если вызываемая функция возвращает.  `mutex` не блокировано поток ожидает, пока условие для освобождения true.  Таким образом, чтобы не будут непредвиденные результаты, каждый поток, который ожидает переменную условия должен использоваться один и тот же объект `mutex`.  
  
 Объекты типа `condition_variable_any` можно использовать с мьютексом любого типа.  Тип мьютекса, используемый не должен предоставить метод `try_lock`.  Объекты типа `condition_variable` можно использовать только с мьютексом типа `unique_lock<mutex>`.  Объекты этого типа могут быть быстрее, чем объекты типа `condition_variable_any<unique_lock<mutex>>`.  
  
 Чтобы ожидать событие, сначала блокируйте его, а затем вызовите один из методов `wait` с переменной условия.  Вызов блокируется `wait` до других сигналов потока переменную условия.  
  
 *Паразитные пробуждения* возникает, когда потоки, ожидающие переменные условий разблокированными без соответствующих уведомлений.  Для распознавания те паразитные пробуждения код ожидает условие для освобождения true должен явно проверить это условие, когда код возврата из функции ожидания.  Обычно это делается с помощью цикла; можно использовать `wait(unique_lock<mutex>& lock, Predicate pred)` щелкните этот цикл автоматически.  
  
```cpp  
while (condition is false)  
    wait for condition variable;  
```  
  
 Классы каждое `condition_variable_any` и `condition_variable` имеют 3 метода, ожидающие условие.  
  
-   `wait` ожидает неограниченный период времени.  
  
-   `wait_until` дождитесь указанного `time`.  
  
-   `wait_for` ожидает определенное `time interval`.  
  
 Каждый из этих методов имеет перегруженные версии 2.  Один — просто ожидает и может проспать вверх паразитно.  Другой принимает дополнительный аргумент шаблона, который определяет предикат.  Метод не возвращает до тех пор, пока не будет предикат `true`.  
  
 Каждый класс также содержит 2 метода, используются для оповещения переменную условия, ее состояние `true`.  
  
-   `notify_one` выводит вверх по одному из потоков, ожидающий переменную условия.  
  
-   `notify_all` выводит вверх по всем потоки, ожидающие переменную условия.  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Класс condition\_variable](../standard-library/condition-variable-class.md)   
 [Класс condition\_variable\_any](../standard-library/condition-variable-any-class.md)   
 [Перечисление cv\_status](../Topic/cv_status%20Enumeration.md)