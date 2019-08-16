---
title: Многопоточность. Создание потоков пользовательского интерфейса MFC
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
ms.openlocfilehash: 1cd28a848f9be223f43412c3e0f3961cef9db6c7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512092"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>Многопоточность. Создание потоков пользовательского интерфейса MFC

Поток пользовательского интерфейса обычно используется для обработки вводимых пользователем данных и реагирования на события пользователя независимо от потоков, выполняющих другие части приложения. Основной поток приложения (предоставленный в `CWinApp`классе, производном от класса) уже создан и запущен. В этом разделе описаны шаги, необходимые для создания дополнительных потоков пользовательского интерфейса.

Первое, что необходимо сделать при создании потока пользовательского интерфейса, — это производный класс от [CWinThread](../mfc/reference/cwinthread-class.md). Этот класс необходимо объявить и реализовать с помощью макросов [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) . Этот класс должен переопределять некоторые функции и может переопределять другие. Эти функции и то, что они должны сделать, представлены в следующей таблице.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Функции, переопределяемые при создании потока пользовательского интерфейса

|Функция|Цель|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|Выполнять очистку при завершении потока. Обычно переопределяется.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|Выполнить инициализацию экземпляра потока. Должен быть переопределен.|
|[Обработчик](../mfc/reference/cwinthread-class.md#onidle)|Выполнение обработки времени простоя для конкретного потока. Обычно не переопределяется.|
|[претранслатемессаже](../mfc/reference/cwinthread-class.md#pretranslatemessage)|Фильтрация сообщений до их отправки в `TranslateMessage` и. `DispatchMessage` Обычно не переопределяется.|
|[процессвндпроцексцептион](../mfc/reference/cwinthread-class.md#processwndprocexception)|Перехват необработанных исключений, вызванных сообщениями потока и обработчиками команд. Обычно не переопределяется.|
|[Выполнить](../mfc/reference/cwinthread-class.md#run)|Управление функцией для потока. Содержит конвейер сообщений. Нередко переопределяются.|

MFC предоставляет две версии `AfxBeginThread` через перегрузку параметров: одну, которая может создавать только рабочие потоки и один, который может создавать потоки пользовательского интерфейса или рабочие потоки. Чтобы запустить поток пользовательского интерфейса, вызовите вторую перегрузку [афксбегинсреад](../mfc/reference/application-information-and-management.md#afxbeginthread), предоставив следующую информацию:

- [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) класса, производного от `CWinThread`.

- Используемых Требуемый уровень приоритета. По умолчанию используется обычная важность. Дополнительные сведения о доступных уровнях приоритета см. в разделе [сетсреадприорити](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) в Windows SDK.

- Используемых Требуемый размер стека для потока. Значение по умолчанию — это тот же стек размеров, что и при создании потока.

- Используемых CREATE_SUSPENDED, если вы хотите, чтобы поток создавался в приостановленном состоянии. Значение по умолчанию — 0 или запустить поток обычным образом.

- Используемых Требуемые атрибуты безопасности. По умолчанию используется тот же доступ, что и для родительского потока. Дополнительные сведения о формате этих сведений о безопасности см. в разделе [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) в Windows SDK.

`AfxBeginThread`выполняет большую часть работы. Он создает новый объект класса, инициализирует его с помощью предоставленной информации и вызывает метод [CWinThread:: CreateThread](../mfc/reference/cwinthread-class.md#createthread) для начала выполнения потока. Проверки выполняются на протяжении всей процедуры, чтобы убедиться, что все объекты освобождены должным образом, в случае сбоя любой части создания.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Многопоточность. Завершение работы с потоками](multithreading-terminating-threads.md)

- [Многопоточность. Создание рабочих потоков](multithreading-creating-worker-threads.md)

- [Процессы и потоки](/windows/win32/ProcThread/processes-and-threads)

## <a name="see-also"></a>См. также

[Реализация многопоточности на языке C++ с помощью классов MFC](multithreading-with-cpp-and-mfc.md)
