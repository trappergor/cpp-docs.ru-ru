---
title: "Структуры данных синхронизации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: synchronization data structures
ms.assetid: d612757d-e4b7-4019-a627-f853af085b8b
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1dd1c47cad01e0324f8027593eb4933f70cd6191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="synchronization-data-structures"></a>Структуры данных синхронизации
Среда выполнения с параллелизмом предоставляет несколько структур данных, которые позволяют синхронизировать доступ к общим данным из нескольких потоков. Эти структуры данных полезны в тех случаях, когда общей редко изменяемых данных. Объект синхронизации, например, критическую секцию, в результате других потоках, подождите, пока общий ресурс недоступен. Таким образом при использовании такой объект для синхронизации доступа к данным, которые часто используются, вы можете потерять масштабируемость приложения. [Библиотеки параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) предоставляет [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс, который дает возможность совместного использования ресурсов среди нескольких потоков или задач без необходимости синхронизации. Дополнительные сведения о `combinable` см. в описании [параллельные контейнеры и объекты](../../parallel/concrt/parallel-containers-and-objects.md).  
  
##  <a name="top"></a> Разделы  
 В этом разделе описываются следующие типы асинхронных блоков сообщений подробно:  
  
-   [critical_section](#critical_section)  
  
-   [reader_writer_lock](#reader_writer_lock)  
  
-   [scoped_lock и scoped_lock_read](#scoped_lock)  
  
-   [event](#event)  
  
##  <a name="critical_section"></a>critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) класс представляет объект совместного взаимного исключения, который уступает другим задачам, а не вытесняет их. Критические секции удобны, когда нескольким потокам требуется монопольный доступ чтение и запись к общим данным.  

 `critical_section` Класс допускает повторные входы. [Concurrency::critical_section:: lock](reference/critical-section-class.md#lock) метод создает исключение типа [concurrency::improper_lock](../../parallel/concrt/reference/improper-lock-class.md) при вызове из потока, уже владеющего блокировкой.  


  
### <a name="methods-and-features"></a>Методы и свойства  
 В следующей таблице показаны важные методы, которые определены в `critical_section` класса.  
  
|Метод|Описание:|  
|------------|-----------------|  
|[lock](reference/critical-section-class.md#lock)|Получает критическую секцию. Вызывающий контекст блокируется, пока не получит блокировку.|  
|[try_lock](reference/critical-section-class.md#try_lock)|Пытается получить критическую секцию, но не выполняет блокировку.|  
|[unlock](reference/critical-section-class.md#unlock)|Освобождает критический раздел.|  
  
 [[В начало](#top)]  
  
##  <a name="reader_writer_lock"></a>reader_writer_lock  
 [Concurrency::reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) класс предоставляет операции потоками чтения и записи к общим данным. Используйте блокировки чтения и записи, если нескольким потокам требуется параллельный доступ для чтения к общему ресурсу, но редко записи для этого общего ресурса. Этот класс предоставляет доступ для записи только один поток на объект в любое время.  
  
 `reader_writer_lock` Класс может выполнять лучше, чем `critical_section` класса, так как `critical_section` получает эксклюзивный доступ к общему ресурсу, который не допускает параллельный доступ для чтения.  
  
 Как `critical_section` класса `reader_writer_lock` представляет объект совместного взаимного исключения, который уступает другим задачам, а не вытесняет их.  
  
 Когда поток, который необходимо записать в общий ресурс получает блокировку чтения и записи, другие потоки, которые также необходимо получить доступ к ресурсу блокируются до записи освобождает блокировку. `reader_writer_lock` Класса является примером *предпочтения записи* блокировки, которая разблокирует ожидающие записывающие потоки до разблокировки ожидающих читающих потоков.  
  
 Как `critical_section` класса `reader_writer_lock` класс допускает повторные входы. [Concurrency::reader_writer_lock:: lock](reference/reader-writer-lock-class.md#lock) и [Concurrency::reader_writer_lock::](reference/reader-writer-lock-class.md#lock_read) методы вызывают исключение типа `improper_lock` , если они вызываются потоком, который уже является владельцем блокировка.  


  
> [!NOTE]
>  Поскольку `reader_writer_lock` класс допускает повторные входы, невозможно повысить уровень блокировки только для чтения до блокировки чтения и записи или понизить уровень блокировки чтения и записи к блокировке только для чтения. Выполнение этих операций приводит к непредсказуемому поведению.  
  
### <a name="methods-and-features"></a>Методы и свойства  
 В следующей таблице показаны важные методы, которые определены в `reader_writer_lock` класса.  
  
|Метод|Описание:|  
|------------|-----------------|  
|[lock](reference/reader-writer-lock-class.md#lock)|Получает доступ на чтение и запись к блокировке.|  
|[try_lock](reference/reader-writer-lock-class.md#try_lock)|Пытается получить доступ на чтение и запись к блокировке, но не выполняет блокировку.|  
|[lock_read](reference/reader-writer-lock-class.md#lock_read)|Получает доступ только для чтения к блокировке.|  
|[try_lock_read](reference/reader-writer-lock-class.md#try_lock_read)|Пытается получить доступ только для чтения до блокировки, но не выполняет блокировку.|  
|[unlock](reference/reader-writer-lock-class.md#unlock)|Снимает блокировку.|  
  
 [[В начало](#top)]  
  
##  <a name="scoped_lock"></a>scoped_lock и scoped_lock_read  
 `critical_section` И `reader_writer_lock` классы предоставляют вложенные вспомогательные классы, упрощающие способ работы с объектами взаимное исключение. Эти вспомогательные классы называются *блокировками с областью*.  
  
 `critical_section` Класс содержит [Concurrency::critical_section:: scoped_lock](reference/critical-section-class.md#critical_section__scoped_lock_class) класса. Конструктор получает доступ к предоставленному `critical_section` объект; деструктор выпуски доступ к этому объекту. `reader_writer_lock` Класс содержит [Concurrency::reader_writer_lock:: scoped_lock](reference/reader-writer-lock-class.md#scoped_lock_class) класс, который имеет вид `critical_section::scoped_lock`, за исключением того, управляющий доступом для записи к предоставленному `reader_writer_lock` объекта. `reader_writer_lock` Класс также содержит [Concurrency::reader_writer_lock:: scoped_lock_read](reference/reader-writer-lock-class.md#scoped_lock_read_class) класса. Этот класс управляет доступом на чтение к предоставленному `reader_writer_lock` объекта.  

  
 Блокировки с областью имеют несколько преимуществ при работе с `critical_section` и `reader_writer_lock` объектов вручную. Как правило вы блокировка с областью размещается в стеке. Блокировка с областью высвобождает доступ к объекту взаимного исключения автоматически при уничтожении; Таким образом вам не требуется вручную разблокировать основной объект. Это полезно, если функция содержит несколько `return` инструкции. Блокировки с областью также помогают писать безопасный в отношении исключений код. Когда `throw` инструкция вызывает стека, вызываются деструкторы всех активных блокировок с областью, и поэтому всегда правильно освобождается объект взаимного исключения.  
  
> [!NOTE]
>  При использовании `critical_section::scoped_lock`, `reader_writer_lock::scoped_lock`, и `reader_writer_lock::scoped_lock_read` классы, не вручную освободить доступ к базовому объекту взаимного исключения. Среда выполнения может перейти в недопустимое состояние.  
  
##  <a name="event"></a>событие  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md) представляет объект синхронизации, состояние которого может выполняться или отсутствовать. В отличие от объектов синхронизации, например критические секции, целью которого является защиты доступа к общим данным, события синхронизируют последовательность выполнения.  
  
 `event` Класс полезен, когда одна задача завершила работу для другой задачи. Например одна задача может сигнализировать другой задаче о завершении чтения данных из сетевого подключения или из файла.  
  
### <a name="methods-and-features"></a>Методы и свойства  
 В следующей таблице показаны некоторые важные методы, которые определены в `event` класса.  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Ожидание](reference/event-class.md#wait)|Ожидание события в сигнальное.|  
|[set](reference/event-class.md#set)|Задает событие в сигнальное состояние.|  
|[reset](reference/event-class.md#reset)|Задает несигнальное состояние события.|  
|[wait_for_multiple](reference/event-class.md#wait_for_multiple)|Ожидает несколько событий в сигнальное.|  

  
### <a name="example"></a>Пример  
 Пример, демонстрирующий использование `event` см. в описании [Сравнение структур данных синхронизации с Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md).  
  
 [[В начало](#top)]  
  
## <a name="related-sections"></a>Связанные разделы  
 [Сравнение структур данных синхронизации с интерфейсом Windows API](../../parallel/concrt/comparing-synchronization-data-structures-to-the-windows-api.md)  
 Сравнивает поведение структур данных синхронизации с журналам, предоставляемым Windows API.  
  
 [Среда выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime.md)  
 Описывает среду выполнения с параллелизмом, которая упрощает процесс параллельного программирования и содержит ссылки на соответствующие разделы.

