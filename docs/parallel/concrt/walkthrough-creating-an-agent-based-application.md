---
title: Пошаговое руководство. Создание приложения на основе агента
ms.date: 11/04/2016
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 1d5e7ed085481b714423760cebf2984084626645
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509348"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>Пошаговое руководство. Создание приложения на основе агента

В этом разделе описывается создание базового приложения на основе агентов. В этом пошаговом руководстве можно создать агент, который считывает данные из текстового файла асинхронно. Приложение использует алгоритм контрольную сумму Adler-32 вычислить контрольную сумму содержимого этого файла.

## <a name="prerequisites"></a>Предварительные требования

Необходимо понять следующие моменты для выполнения этого пошагового руководства:

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

В этом разделе показано, как создать консольное приложение Visual C++, который ссылается на файлы заголовков, которые будут использоваться программой.

#### <a name="to-create-a-visual-c-application-by-using-the-win32-console-application-wizard"></a>Для создания приложения Visual C++ с помощью мастера приложений Win32 консоли

1. На **файл** меню, щелкните **New**, а затем нажмите кнопку **проекта** для отображения **новый проект** диалоговое окно.

1. В **новый проект** выберите **Visual C++** узел в **типы проектов** панели, а затем выберите **консольное приложение Win32** в **шаблоны** области. Например, введите имя проекта, `BasicAgent`, а затем нажмите кнопку **ОК** для отображения **мастер консольного приложения Win32**.

1. В **мастер консольного приложения Win32** диалоговом окне щелкните **Готово**.

1. В файле stdafx.h добавьте следующий код.

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Файл заголовка agents.h содержит функциональные возможности [concurrency::agent](../../parallel/concrt/reference/agent-class.md) класса.

1. Убедитесь, что приложение успешно создан путем создания и выполнения его. Для построения приложения, на **построения** меню, щелкните **построить решение**. Если сборка приложения прошла успешно, запустите приложение, выбрав **начать отладку** на **Отладка** меню.

[[В начало](#top)]

##  <a name="createagentclass"></a> Создание file_reader класса

В этом разделе показано, как создать `file_reader` класса. Среда выполнения назначает каждого агента для выполнения работы в своем собственном контексте. Таким образом можно создать агент, который выполняет работу синхронно, но взаимодействует с другими компонентами асинхронно. `file_reader` Класс считывает данные из заданного входного файла и отправляет данные из этого файла в компонент заданного целевого объекта.

#### <a name="to-create-the-filereader-class"></a>Чтобы создать класс file_reader

1. Добавьте новый файл заголовка C++ в проект. Для этого щелкните правой кнопкой мыши **файлы заголовков** узел в **обозревателе решений**, нажмите кнопку **добавить**, а затем нажмите кнопку **новый элемент**. В **шаблоны** области выберите **файл заголовка (.h)**. В **Добавление нового элемента** диалоговом окне `file_reader.h` в **имя** поле и нажмите кнопку **добавить**.

1. В файле file_reader.h добавьте следующий код.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. В файле file_reader.h создайте класс с именем `file_reader` , наследуемый от класса `agent`.

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Добавьте следующие данные-члены `private` части вашего класса.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   `_file_name` Член является имя файла, который агент считывает данные из. `_target` Член является [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) объекта, который агент записывает содержимое файла. `_error` Член содержит любая ошибка, возникающая во время работы агента.

1. Добавьте следующий код для `file_reader` конструкторы `public` раздел `file_reader` класса.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Каждая перегрузка конструктора задает `file_reader` данные-члены. Перегрузки конструктора, второй и третий позволяет вашему приложению, использование определенного планировщика с агентом. Первая перегрузка использует планировщик по умолчанию с агентом.

1. Добавить `get_error` метод в общем разделе класса `file_reader` класса.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   `get_error` Метод извлекает любая ошибка, возникающая во время работы агента.

1. Реализуйте [Concurrency::agent:: Run](reference/agent-class.md#run) метод в `protected` части вашего класса.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

`run` Метод открывает файл и считывает данные из него. `run` Метод использует обработку исключений, чтобы записать все ошибки, возникающие во время обработки файлов.

   Каждый раз, когда этот метод считывает данные из файла, он вызывает [concurrency::asend](reference/concurrency-namespace-functions.md#asend) функцию для отправки данных в целевой буфер. Целевой буфер для обозначения конца обработки, он отправляет пустую строку.

В следующем примере полное содержимое файла file_reader.h.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[[В начало](#top)]

##  <a name="useagentclass"></a> С помощью file_reader класс в приложении

В этом разделе показано, как использовать `file_reader` класс для считывания содержимого текстового файла. Также показано, как создать [concurrency::call](../../parallel/concrt/reference/call-class.md) объект, который получает данные файла и вычисляет их контрольную сумму Adler-32.

#### <a name="to-use-the-filereader-class-in-your-application"></a>Использование класса file_reader в приложении

1. В BasicAgent.cpp, добавьте следующий `#include` инструкции.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. В BasicAgent.cpp, добавьте следующий `using` директивы.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. В `_tmain` функцию, создайте [concurrency::event](../../parallel/concrt/reference/event-class.md) , сообщающий о завершении обработки.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Создание `call` объекта, изменяет контрольную сумму, при получении данных.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Это `call` объекта также задает `event` объекта при получении пустую строку для обозначения окончания обработки.

1. Создание `file_reader` объект, который считывает из файла test.txt и записывает содержимое этого файла значение `call` объекта.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Запустить агент и дождитесь его завершения.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. Дождитесь `call` объект для получения всех данных и Готово.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Проверьте наличие ошибок чтения файла. Если ошибок не обнаружено, вычислить окончательный сумму Adler-32 и печати суммы на консоль.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

В следующем примере полный файл BasicAgent.cpp.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[[В начало](#top)]

## <a name="sample-input"></a>Входные данные выборки

Это пример содержимого входного файла text.txt:

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Пример результатов выполнения

При использовании примера входных данных, эта программа создает следующие выходные данные:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы предотвратить одновременный доступ к членам данных, рекомендуется добавить методы, выполняющие работу по `protected` или `private` части вашего класса. Добавить только методы, которые отправляют или получают сообщения между агентом `public` части вашего класса.

Всегда вызывайте метод [concurrency::agent:: сделать](reference/agent-class.md#done) метод для перевода агента в завершенное состояние. Обычно этот метод вызывается до возврата `run` метод.

## <a name="next-steps"></a>Следующие шаги

Еще одним примером приложения на основе агентов, см. в разделе [Пошаговое руководство: использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md).

## <a name="see-also"></a>См. также

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)

