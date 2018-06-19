---
title: 'Пошаговое руководство: Создание приложения на основе агентов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78826bb9f00e77a80fb65dd3a3ceda7eedb38796
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692630"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>Пошаговое руководство. Создание приложения на основе агента
В этом разделе описывается создание базового приложения на основе агентов. В этом пошаговом руководстве можно создать агент, который асинхронно считывает данные из текстового файла. Приложение использует алгоритм контрольной суммы Adler-32 для расчета контрольной суммы содержимого этого файла.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо ознакомиться со следующими разделами, для выполнения данного пошагового руководства:  
  
- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)  
  
- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)  
  
- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)  
  
- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)  
  
##  <a name="top"></a> Разделы  
 В этом пошаговом руководстве показано, как выполнять следующие задачи:  
  
- [Создание консольного приложения](#createapplication)  
  
- [Создание file_reader класса](#createagentclass)  
  
- [С помощью file_reader класс в приложении](#useagentclass)  
  
##  <a name="createapplication"></a> Создание консольного приложения  
 В этом разделе показано создание консольного приложения Visual C++, ссылки на файлы заголовка, которые будут использоваться программой.  
  
#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Создание приложения Visual C++ с помощью мастера консольных приложений Win32  
  
1.  На **файл** меню, нажмите кнопку **New**и нажмите кнопку **проекта** для отображения **новый проект** диалоговое окно.  
  
2.  В **новый проект** выберите **Visual C++** узел в **типов проектов** панели, а затем выберите **консольное приложение Win32** в **шаблоны** области. Введите имя проекта, например `BasicAgent`, а затем нажмите кнопку **ОК** для отображения **мастер консольного приложения Win32**.  
  
3.  В **мастер консольного приложения Win32** диалоговое окно, нажмите кнопку **Готово**.  
  
4.  В файле stdafx.h добавьте следующий код.  
  
 [!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]  
  
     Файл заголовка agents.h содержит функциональные возможности [concurrency::agent](../../parallel/concrt/reference/agent-class.md) класса.  
  
5.  Убедитесь, что приложение успешно создано, построения и выполнения его. Для сборки приложения, в **построения** меню, нажмите кнопку **построить решение**. Если сборка приложения прошла успешно, запустите приложение, нажав кнопку **начать отладку** на **отладки** меню.  
  
 [[В начало](#top)]  
  
##  <a name="createagentclass"></a> Создание file_reader класса  
 В этом разделе показано, как создать `file_reader` класса. Планирование в среде выполнения каждого агента для выполнения работы в его собственном контексте. Таким образом можно создать агент, выполняющий работу синхронно, но взаимодействует с другими компонентами асинхронно. `file_reader` Класс считывает данные из заданного входного файла и отправляет данные из этого файла заданному целевому компоненту.  
  
#### <a name="to-create-the-filereader-class"></a>Чтобы создать класс file_reader  
  
1.  Добавьте новый файл заголовка C++ в проект. Чтобы сделать это, щелкните правой кнопкой мыши **файлы заголовков** узел в **обозревателе решений**, нажмите кнопку **добавить**и нажмите кнопку **новый элемент**. В **шаблоны** выберите **заголовочный файл (.h)**. В **Добавление нового элемента** диалоговом `file_reader.h` в **имя** и нажмите кнопку **добавить**.  
  
2.  В файле file_reader.h добавьте следующий код.  
  
 [!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]  
  
3.  В файле file_reader.h создайте класс с именем `file_reader` , производный от `agent`.  
  
 [!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]  
  
4.  Добавьте следующие данные-члены `private` секцию этого класса.  
  
 [!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]  
  
     `_file_name` Член является имя файла, в который агент считывает данные из. `_target` Член является [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) объекта, который агент записывает содержимое файла. `_error` Член содержит все ошибки, происходящие во время работы агента.  
  
5.  Добавьте следующий код для `file_reader` конструкторов, чтобы `public` раздел `file_reader` класса.  
  
 [!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]  
  
     Каждая перегрузка конструктора задает `file_reader` членов данных. Перегрузки конструктора, второй и третий позволяет приложению использовать с агентом конкретный планировщик. Первая перегрузка использует планировщик по умолчанию с агентом.  
  
6.  Добавить `get_error` метод открытого раздел `file_reader` класса.  
  
 [!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]  
  
     `get_error` Метод извлекает любые ошибки, происходящие во время работы агента.  
  

7.  Реализуйте [Concurrency::agent:: Run](reference/agent-class.md#run) метод в `protected` секцию этого класса.  

  
 [!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]  
  
`run` Метод открывает файл и считывает из него данные. `run` Метод использует обработку исключений, чтобы регистрировать ошибки, возникающие во время обработки файлов.  
  
   Каждый раз, этот метод считывает данные из файла, он вызывает [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функции, чтобы отправить данные в целевой буфер. Целевой буфер для обозначения конца обработки, он отправляет пустая строка.  

  
 В следующем примере полное содержимое файла file_reader.h.  
  
 [!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]  
  
 [[В начало](#top)]  
  
##  <a name="useagentclass"></a> С помощью file_reader класс в приложении  
 В этом разделе показано, как использовать `file_reader` класса для считывания содержимого текстового файла. Также демонстрируется создание [concurrency::call](../../parallel/concrt/reference/call-class.md) объект, который получает данные файла и вычисляет их контрольную сумму Adler-32.  
  
#### <a name="to-use-the-filereader-class-in-your-application"></a>Использование класса file_reader в приложении  
  
1.  В BasicAgent.cpp, добавьте следующий `#include` инструкции.  
  
 [!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]  
  
2.  В BasicAgent.cpp, добавьте следующий `using` директивы.  
  
 [!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]  
  
3.  В `_tmain` функции, создайте [concurrency::event](../../parallel/concrt/reference/event-class.md) объекта, который сигнализирует о завершении обработки.  
  
 [!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]  
  
4.  Создание `call` , обновляющий контрольную сумму при получении данных.  
  
 [!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]  
  
     Это `call` объекта также задает `event` объекта при получении пустой строки в качестве сигнала о завершении обработки.  
  
5.  Создание `file_reader` объект, который считывает из файла test.txt и записывает содержимое этого файла значение `call` объекта.  
  
 [!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]  
  
6.  Запустите агент и дождитесь его завершения.  
  
 [!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]  
  
7.  Дождитесь `call` объекта для получения всех данных и завершения.  
  
 [!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]  
  
8.  Проверьте наличие ошибок в модуле чтения файлов. Если ошибки не возникают, вычислить окончательный сумму Adler-32 и выведите сумму на консоль.  
  
 [!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]  
  
 В примере показан полный файл BasicAgent.cpp.  
  
 [!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]  
  
 [[В начало](#top)]  
  
## <a name="sample-input"></a>Входные данные выборки  
 Вот пример содержимого входного файла text.txt.  
  
```Output  
The quick brown fox  
jumps  
over the lazy dog  
```  
  
## <a name="sample-output"></a>Пример результатов выполнения  
 При использовании с входные данные выборки, эта программа создает следующие выходные данные:  
  
```Output  
Adler-32 sum is fefb0d75  
```  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Чтобы предотвратить одновременный доступ к членам данных, рекомендуется добавить методы, выполняющие работу по `protected` или `private` секцию этого класса. Добавлять только методы, которые отправляют или получают сообщения от агента `public` секцию этого класса.  
  

 Всегда вызывайте метод [concurrency::agent:: сделать](reference/agent-class.md#done) метод для перевода агента в завершенное состояние. Обычно этот метод вызывается до возврата из `run` метод.  

  
## <a name="next-steps"></a>Следующие шаги  
 Еще один пример приложения на основе агентов см. в разделе [Пошаговое руководство: использование класса join для предотвращения взаимоблокировок](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)   
 [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)   
 [Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

