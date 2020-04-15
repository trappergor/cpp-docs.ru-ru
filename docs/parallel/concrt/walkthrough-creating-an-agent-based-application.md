---
title: Пошаговое руководство. Создание приложения на основе агента
ms.date: 04/25/2019
helpviewer_keywords:
- asynchronous agents, creating
- agent class, example
ms.assetid: 730f42ce-6d58-4753-b948-fd9c9ef2ce6c
ms.openlocfilehash: 20197786e3d3c2d34d29af748c1cc073902cf70d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377455"
---
# <a name="walkthrough-creating-an-agent-based-application"></a>Пошаговое руководство. Создание приложения на основе агента

Эта тема описывает, как создать базовое приложение на основе агента. В этом пошаговом шаге можно создать агент, который считывает данные из текстового файла асинхронно. Приложение использует алгоритм проверки Адлер-32 для расчета проверки содержимого этого файла.

## <a name="prerequisites"></a>Предварительные требования

Вы должны понимать следующие темы, чтобы завершить это пошагза:

- [Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)

- [Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)

## <a name="sections"></a><a name="top"></a>Разделы

В этом пошаговом показании, как выполнять следующие задачи:

- [Создание консольного приложения](#createapplication)

- [Создание класса file_reader](#createagentclass)

- [Использование file_reader класса в приложении](#useagentclass)

## <a name="creating-the-console-application"></a><a name="createapplication"></a>Создание консольного приложения

В этом разделе показано, как создать консольное приложение СЗ, которое ссылается на файлы заголовка, которые будет использовать программа. Начальные шаги варьируются в зависимости от того, какую версию Visual Studio вы используете. Чтобы просмотреть документацию для предпочтительной версии Visual Studio, используйте элемент управления селектора **версии.** Он находится в верхней части таблицы содержимого на этой странице.

::: moniker range="vs-2019"

### <a name="to-create-a-c-console-application-in-visual-studio-2019"></a>Для создания консольного приложения с КЗ в Visual Studio 2019

1. В главном меню выберите **Файл ** > **Создать ** > **Проект**, чтобы открыть диалоговое окно **Создание проекта**.

1. В верхней части диалогового окна для параметра **Язык** выберите значение **C++**, для параметра **Платформа** — значение **Windows**, а для параметра **Тип проекта** — значение **Консоль**.

1. В отфильтрованном списке типов проектов щелкните **Консольное приложение**, а затем нажмите кнопку **Далее**. На следующей странице `BasicAgent` введите название проекта и при желании укажите местоположение проекта.

1. Нажмите кнопку **Создать**, чтобы создать проект.

1. Нажмите правой кнопкой наузло узла проекта в **Solution Explorer**и выберите **Свойства.** В соответствии с **конфигурацией Свойства** > **C / C е** > **Предварительно компилированные заголовки** > **Предварительно заголовок** выбрать **Создать**.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-c-console-application-in-visual-studio-2017-and-earlier"></a>Для создания консольного приложения с КЗ в Visual Studio 2017 и ранее

1. В меню **файла** нажмите **«Новый»,** а затем нажмите **«Проект»,** чтобы отобразить диалоговую коробку **Нового проекта.**

1. В диалоговом окне **нового проекта** выберите узла **Visual C's** в панели **типов проектов,** а затем выберите **консольное приложение Win32** в панели **шаблонов.** Например, введите имя `BasicAgent`для проекта, а затем нажмите **OK,** чтобы отобразить **Мастера консольных приложений Win32.**

1. В диалоговом окне **Win32 Console Application Wizard** нажмите **«Завершение».**

::: moniker-end

1. В *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее) добавьте следующий код:

[!code-cpp[concrt-basic-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_1.h)]

   Файл заголовка agents.h содержит функциональность [параллелизма::агент](../../parallel/concrt/reference/agent-class.md) класса.

1. Убедитесь, что приложение было успешно создано путем его создания и запуска. Чтобы построить приложение, в меню **сборки,** нажмите **Разрешение сборки**. Если приложение успешно построено, запустите приложение, нажав кнопку **Start Debugging** в меню **Debug.**

[Сверху](#top)

## <a name="creating-the-file_reader-class"></a><a name="createagentclass"></a>Создание класса file_reader

В этом разделе показано, как создать `file_reader` класс. Время выполнения планирует каждому агенту выполнять работу в своем контексте. Таким образом, можно создать агент, который выполняет работу синхронно, но взаимодействует с другими компонентами асинхронно. Класс `file_reader` считывает данные из данного входним файла и отправляет данные из этого файла в данный целевой компонент.

#### <a name="to-create-the-file_reader-class"></a>Создание класса file_reader

1. Добавьте в проект новый файл заголовка «СИ» . Чтобы сделать это, правой кнопкой мыши **заголовок файлы** узел в **Solution Explorer**, нажмите **Добавить**, а затем нажмите **Новый пункт**. В панели **шаблонов** выберите **файл заголовка (.h).** В диалоговом поле **Добавить новый элемент** введите `file_reader.h` поле **Name,** а затем нажмите **Добавить**.

1. В file_reader.h добавьте следующий код.

[!code-cpp[concrt-basic-agent#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_2.h)]

1. В file_reader.h, создайте класс, который `file_reader` `agent`называется, который происходит от .

[!code-cpp[concrt-basic-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_3.h)]

1. Добавьте следующие участники данных в `private` раздел вашего класса.

[!code-cpp[concrt-basic-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_4.h)]

   Участник `_file_name` — это имя файла, из которого агент читает. Участник `_target` является [параллелью::ITarget](../../parallel/concrt/reference/itarget-class.md) объект, на который агент записывает содержимое файла. Участник `_error` содержит любую ошибку, которая происходит в течение жизни агента.

1. Добавьте следующий `file_reader` код для конструкторов `public` в `file_reader` раздел класса.

[!code-cpp[concrt-basic-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_5.h)]

   Каждый конструктор перегрузки `file_reader` устанавливает членов данных. Перегрузка второго и третьего конструкторов позволяет приложению использовать определенный планировщик с вашим агентом. Первая перегрузка использует планировщик по умолчанию с вашим агентом.

1. Добавьте `get_error` метод в общедоступный `file_reader` раздел класса.

[!code-cpp[concrt-basic-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_6.h)]

   Метод `get_error` извлекает любую ошибку, которая происходит в течение срока службы агента.

1. Реализация [параллелизма::агент::Запуск](reference/agent-class.md#run) `protected` метода в разделе вашего класса.

[!code-cpp[concrt-basic-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_7.h)]

Метод `run` открывает файл и считывает данные из него. Метод `run` использует обработку исключений для фиксации ошибок, возникающих при обработке файлов.

   Каждый раз, когда этот метод считывает данные из файла, он называет [параллелизм::функция отправки](reference/concurrency-namespace-functions.md#asend) этих данных в целевой буфер. Он отправляет пустую строку в целевой буфер, чтобы указать конец обработки.

Ниже приводится полное содержание file_reader.h.

[!code-cpp[concrt-basic-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_8.h)]

[Сверху](#top)

## <a name="using-the-file_reader-class-in-the-application"></a><a name="useagentclass"></a>Использование file_reader класса в приложении

В этом разделе показано, как использовать `file_reader` класс для чтения содержимого текстового файла. Он также показывает, как создать [параллел::объект вызова,](../../parallel/concrt/reference/call-class.md) который получает эти данные файла и вычисляет его проверку Адлер-32.

#### <a name="to-use-the-file_reader-class-in-your-application"></a>Использование file_reader класса в приложении

1. В BasicAgent.cpp добавьте `#include` следующее заявление.

[!code-cpp[concrt-basic-agent#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_9.cpp)]

1. В BasicAgent.cpp добавьте `using` следующие директивы.

[!code-cpp[concrt-basic-agent#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_10.cpp)]

1. В `_tmain` функции создайте [параллелизм::объект события,](../../parallel/concrt/reference/event-class.md) который сигнализирует о конце обработки.

[!code-cpp[concrt-basic-agent#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_11.cpp)]

1. Создайте `call` объект, который обновляет чековую сумму при походе данных.

[!code-cpp[concrt-basic-agent#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_12.cpp)]

   Этот `call` объект также `event` устанавливает объект, когда он получает пустую строку, чтобы сигнализировать о конце обработки.

1. Создайте `file_reader` объект, который читается из файла test.txt `call` и записывает содержимое этого файла объекту.

[!code-cpp[concrt-basic-agent#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_13.cpp)]

1. Запустите агента и подождите, пока он закончится.

[!code-cpp[concrt-basic-agent#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_14.cpp)]

1. Подождите, `call` пока объект получит все данные и закончит.

[!code-cpp[concrt-basic-agent#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_15.cpp)]

1. Проверьте считыватель файлов на наличие ошибок. Если ошибки не произошло, вычислите окончательную сумму Адлер-32 и распечатайте сумму на консоль.

[!code-cpp[concrt-basic-agent#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_16.cpp)]

В следующем примере показан полный файл BasicAgent.cpp.

[!code-cpp[concrt-basic-agent#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-agent-based-application_17.cpp)]

[Сверху](#top)

## <a name="sample-input"></a>Пример ввода

Это содержимое образца входиного файла text.txt:

```Output
The quick brown fox
jumps
over the lazy dog
```

## <a name="sample-output"></a>Пример выходных данных

При использовании с ввоза миноносного образца эта программа производит следующий выход:

```Output
Adler-32 sum is fefb0d75
```

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы предотвратить параллельный доступ к членам данных, мы рекомендуем `protected` добавить методы, выполняющие работу, в раздел вашего класса или `private` в разделе. Только добавляйте методы, которые отправляют или получают `public` сообщения или от агента, в раздел вашего класса.

Всегда звоните [в параллел::агент::dодин](reference/agent-class.md#done) метод перемещения агента в завершенное состояние. Обычно этот метод можно вызвать `run` перед возвращением из метода.

## <a name="next-steps"></a>Next Steps

Для другого примера приложения на [Walkthrough: Using join to Prevent Deadlock](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)основе агента см.

## <a name="see-also"></a>См. также раздел

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md)<br/>
[Пошаговое руководство. Использование класса join для предотвращения взаимоблокировки](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)
