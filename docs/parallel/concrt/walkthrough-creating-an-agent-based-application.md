---
title: "Пошаговое руководство. Создание приложения на основе агента | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "асинхронные агенты, создание"
  - "класс agent, пример"
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
caps.latest.revision: 24
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пошаговое руководство. Создание приложения на основе агента
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В этом разделе описывается создание основного приложения на основе агентов.  В этом пошаговом руководстве показано создание агента, который асинхронно считывает данные из текстового файла.  Приложение использует алгоритм контрольной суммы Adler\-32 для расчета контрольной суммы содержимого этого файла.  
  
## Обязательные компоненты  
 Перед работой с этим пошаговым руководством необходимо ознакомиться со следующими разделами.  
  
-   [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
-   [Структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md)  
  
##  <a name="top"></a> Подразделы  
 В этом пошаговом руководстве показано выполнение следующих задач.  
  
-   [Создание консольного приложения](#createApplication)  
  
-   [Создание класса file\_reader](#createAgentClass)  
  
-   [Использование класса file\_reader в приложении](#useAgentClass)  
  
##  <a name="createApplication"></a> Создание консольного приложения  
 В этом подразделе показано создание консольного приложения Visual C\+\+, ссылающегося на файлы заголовков, которые будут использоваться в программе.  
  
#### Создание приложения Visual C\+\+ с помощью мастера консольных приложений Win32  
  
1.  В меню **Файл** последовательно щелкните **Создать** и **Проект**, чтобы открыть диалоговое окно **Новый проект**.  
  
2.  В диалоговом окне **Новый проект** в области **Типы проектов** выберите узел **Visual C\+\+**, затем выберите **Консольное приложение Win32** в области **Шаблоны**.  Введите имя проекта, например `BasicAgent`, затем нажмите кнопку **ОК**, чтобы отобразить **Мастер консольных приложений Win32**.  
  
3.  В диалоговом окне **Мастера консольных приложений Win32** нажмите кнопку **Готово**.  
  
4.  Добавьте в файл stdafx.h следующий код.  
  
     [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_1.h)]  
  
     Заголовочный файл agents.h содержит функциональные возможности класса [concurrency::agent](../../parallel/concrt/reference/agent-class.md).  
  
5.  Убедитесь, что приложение было успешно создано, выполнив его построение и запуск.  Для построения приложения в меню **Построение** выберите команду **Построить решение**.  Если построение приложения выполнено успешно, запустите приложение, нажав кнопку **Начать отладку** в меню **Отладка**.  
  
 \[[Наверх](#top)\]  
  
##  <a name="createAgentClass"></a> Создание класса file\_reader  
 В этом подразделе показано, как создать класс `file_reader`.  Среда выполнения планирует выполнение работы каждым агентом в его собственном контексте.  Следовательно, можно создать агент, выполняющий работу синхронно, но взаимодействующий с другими компонентами асинхронно.  Класс `file_reader` считывает данные из заданного входного файла и отправляет данные из этого файла заданному целевому компоненту.  
  
#### Создание класса file\_reader  
  
1.  Добавьте в проект новый файл заголовка С\+\+.  Для этого в **обозревателе решений** щелкните правой кнопкой мыши узел **Файлы заголовков**, щелкните **Добавить** и выберите **Новый элемент**.  В области **Шаблоны** выберите пункт **Файл заголовка \(.h\)**.  В диалоговом окне **Добавление нового элемента** введите `file_reader.h` в поле **Имя** и нажмите кнопку **Добавить**.  
  
2.  Добавьте следующий код в файл file\_reader.h.  
  
     [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  В файле file\_reader.h создайте класс с именем `file_reader`, производный от `agent`.  
  
     [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  В секцию `private` этого класса добавьте следующие члены данных.  
  
     [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_4.h)]  
  
     Член `_file_name` представляет собой имя файла, из которого выполняет считывание агент.  Член `_target` представляет собой объект [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md), в который агент записывает содержимое файла.  Член `_error` содержит все ошибки, происходящие за время существования агента.  
  
5.  Добавьте в секцию `public` класса `file_reader` следующий код для конструкторов `file_reader`.  
  
     [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_5.h)]  
  
     Каждая перегрузка конструктора задает члены данных `file_reader`.  Вторая и третья перегрузки конструктора позволяют приложению использовать с агентом конкретный планировщик.  Первая перегрузка использует с агентом планировщик по умолчанию.  
  
6.  Добавьте метод `get_error` в открытую секцию класса `file_reader`.  
  
     [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_6.h)]  
  
     Метод `get_error` извлекает любые ошибки, происходящие за время существования агента.  
  
7.  Реализуйте метод [concurrency::agent::run](../Topic/agent::run%20Method.md) в разделе `protected` класса.  
  
     [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_7.h)]  
  
     Метод `run` открывает файл и считывает из него данные.  Метод `run` использует обработку исключений для фиксирования любых ошибок, происходящих во время обработки файлов.  
  
     При каждом считывании данных из файла этот метод вызывает функцию [concurrency::asend](../Topic/asend%20Function.md), чтобы отправить данные в целевой буфер.  Он отправляет в целевой буфер пустую строку, чтобы указать, что обработка завершена.  
  
 В следующем примере показано полное содержимое файла file\_reader.h.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_8.h)]  
  
 \[[Наверх](#top)\]  
  
##  <a name="useAgentClass"></a> Использование класса file\_reader в приложении  
 В этом подразделе показано использование класса `file_reader` для чтения содержимого текстового файла.  Кроме того, в нем показано, как создавать объект [concurrency::call](../../parallel/concrt/reference/call-class.md), который получает данные файла и вычисляет их контрольную сумму Adler\-32.  
  
#### Использование класса file\_reader в приложении  
  
1.  В файл BasicAgent.cpp добавьте следующий оператор `#include`.  
  
     [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  В файл BasicAgent.cpp добавьте следующие директивы `using`.  
  
     [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  В функции `_tmain` создайте объект [concurrency::event](../Topic/event%20Class.md), сигнализирующий о завершении обработки.  
  
     [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  Создайте объект `call`, обновляющий контрольную сумму при получении данных.  
  
     [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     При получении пустой строки в качестве сигнала о завершении обработки этот объект `call` также задает объект `event`.  
  
5.  Создайте объект `file_reader`, считывающий данные из файла test.txt и записывающий содержимое этого файла в объект `call`.  
  
     [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  Запустите агент и дождитесь его завершения.  
  
     [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  Дождитесь получения объектом `call` всех данных и завершения его работы.  
  
     [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  Проверьте наличие ошибок в модуле чтения файлов.  Если ошибок не обнаружено, рассчитайте окончательную сумму Adler\-32 и выведите сумму на консоль.  
  
     [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 В следующем примере показан полный файл BasicAgent.cpp.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/CPP/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 \[[Наверх](#top)\]  
  
## Пример ввода  
 Далее представлен пример содержимого входного файла text.txt.  
  
  **Быстрая коричневая лиса**  
**перепрыгивает**  
**ленивую собаку**   
## Пример результатов выполнения  
 Если используются входные данные, представленные в примере, программа на выходе дает следующий результат.  
  
  **Сумма Adler\-32 — fefb0d75**   
## Надежное программирование  
 Чтобы запретить одновременный доступ к членам данных, рекомендуется добавить методы, выполняющие работу, в секцию `protected` или `private` используемого класса.  В секцию `public` этого класса следует добавлять только методы, которые отправляют сообщения в агент или получают сообщения от него.  
  
 Всегда вызывайте метод [concurrency::agent::done](../Topic/agent::done%20Method.md) для перевода агента в завершенное состояние.  Как правило, этот метод вызывается до возврата метода `run`.  
  
## Следующие действия  
 Еще один пример приложения на основе агентов см. в разделе [Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md)   
 [Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)