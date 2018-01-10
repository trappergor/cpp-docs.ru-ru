---
title: "Многопоточность: Создание потоков пользовательского интерфейса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 105685e0db4689978ef1e6f8615bb5e5f8acdd43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-creating-user-interface-threads"></a>Многопоточность. Создание потоков пользовательского интерфейса
Поток пользовательского интерфейса обычно используется для обработки входных данных пользователя и реагировать на события пользователя независимо от потоков, выполняющихся на другие части приложения. Основной поток приложения (в вашей `CWinApp`-производный класс) создается и запускается автоматически. В этом разделе описаны шаги, необходимые для создания пользовательского интерфейса дополнительных потоков.  
  
 Первое, что необходимо сделать при создании потока пользовательского интерфейса — производный класс [CWinThread](../mfc/reference/cwinthread-class.md). Необходимо объявить и реализовать класс с помощью [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) и [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) макросы. Этот класс должен переопределять некоторые функции и может переопределить некоторые другие. В следующей таблице представлены эти функции и что следует делать.  
  
### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Переопределяемые функции при создании потока пользовательского интерфейса  
  
|Функция|Цель|  
|--------------|-------------|  

|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)| Выполните очистку после завершения потока. Обычно переопределяется. |  
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)| Выполните инициализацию экземпляра для потока. Должен быть переопределен. |  
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)| Выполните обработку времени простоя для конкретного потока. Обычно не переопределяется. |  
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)| Фильтровать сообщения перед их передачей **TranslateMessage** и **DispatchMessage**. Обычно не переопределяется. |  
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)| Перехвата необработанных исключений, обработчиками команд и сообщений в потоке. Обычно не переопределяется. |  
|[Запустите](../mfc/reference/cwinthread-class.md#run)| Функции управления для потока. Содержит цикл обработки сообщений. Переопределяется редко. |  

  
 MFC предоставляет две версии `AfxBeginThread` посредством параметра перегрузки:, можно создать только рабочие потоки и который может создаваться пользовательского интерфейса и рабочие потоки. Чтобы запустить поток пользовательского интерфейса, вызовите вторую перегрузку [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), указав следующие сведения:  
  
-   [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) класса, производным от `CWinThread`.  
  
-   (Необязательно) Уровень необходимый приоритет. Значение по умолчанию используется обычный приоритет. Дополнительные сведения о доступных уровнях приоритета см. в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
-   (Необязательно) Размер требуемой стека для потока. По умолчанию используется тот же размер стека, что и для создания потока.  
  
-   (Необязательно) **CREATE_SUSPENDED** Если требуется, чтобы поток мог быть создан в приостановленном состоянии. Значение по умолчанию равно 0 или запустить поток в обычном режиме.  
  
-   (Необязательно) Атрибуты требуемой безопасности. Значение по умолчанию — такой же доступ, как родительского потока. Дополнительные сведения о формате информации о безопасности см. в разделе [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread`выполняет большую часть работы. Она создает новый объект класса, инициализирует его с данные вводятся и вызывает [функцию CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) для запуска выполнения потока. Проверяет вносятся во всей процедуры, убедитесь, что все объекты, освобожденных должным образом вызывать любую часть создания.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Многопоточность. Завершение потоков](../parallel/multithreading-terminating-threads.md)  
  
-   [Многопоточность. Создание рабочих потоков](../parallel/multithreading-creating-worker-threads.md)  
  
-   [Процессы и потоки](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C++ с помощью классов MFC](../parallel/multithreading-with-cpp-and-mfc.md)