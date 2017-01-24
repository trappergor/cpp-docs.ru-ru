---
title: "CWinThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinThread - класс"
  - "работа с потоками [MFC], создание потоков"
  - "работа с потоками [MFC], безопасность"
  - "рабочие потоки"
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс, представляющий поток исполнения в приложении.  
  
## Синтаксис  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinThread::CWinThread](../Topic/CWinThread::CWinThread.md)|Создает объект `CWinThread`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)|Начинается выполнение объекта `CWinThread`.|  
|[CWinThread::ExitInstance](../Topic/CWinThread::ExitInstance.md)|Переопределение для очистки когда поток завершается.|  
|[CWinThread::GetMainWnd](../Topic/CWinThread::GetMainWnd.md)|Извлекает указатель на главное окно для потока.|  
|[CWinThread::GetThreadPriority](../Topic/CWinThread::GetThreadPriority.md)|Возвращает приоритет текущего потока.|  
|[CWinThread::InitInstance](../Topic/CWinThread::InitInstance.md)|Переопределение для инициализации экземпляра потока.|  
|[CWinThread::IsIdleMessage](../Topic/CWinThread::IsIdleMessage.md)|Проверяет наличие специальных сообщений.|  
|[CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md)|Переопределение для выполнения обработки времени простоя поток\- в XML\-структуру.|  
|[CWinThread::PostThreadMessage](../Topic/CWinThread::PostThreadMessage.md)|Создает сообщение с другим объектом `CWinThread`.|  
|[CWinThread::PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|Сообщения фильтров, прежде чем они отправляются в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](../Topic/CWinThread::ProcessMessageFilter.md)|Некоторые перехватывает сообщения до того, как они достигнут приложения.|  
|[CWinThread::ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|Перехватывает все необработанные исключения, вызываемые обработчиков сообщений и команды потока.|  
|[CWinThread::PumpMessage](../Topic/CWinThread::PumpMessage.md)|Содержит цикл обработки сообщений потока.|  
|[CWinThread::ResumeThread](../Topic/CWinThread::ResumeThread.md)|Уменьшает счетчик приостановки работы потока.|  
|[CWinThread::Run](../Topic/CWinThread::Run.md)|Функции управления для потоков с сообщением нагнетает.  Переопределение настраивать по умолчанию цикл обработки сообщений.|  
|[CWinThread::SetThreadPriority](../Topic/CWinThread::SetThreadPriority.md)|Задает приоритет текущего потока.|  
|[CWinThread::SuspendThread](../Topic/CWinThread::SuspendThread.md)|Увеличивает число поток приостановить.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinThread::operator HANDLE](../Topic/CWinThread::operator%20HANDLE.md)|Получает дескриптор объекта `CWinThread`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinThread::m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md)|Определяет, является ли объект уничтожен при завершении потока.|  
|[CWinThread::m\_hThread](../Topic/CWinThread::m_hThread.md)|Дескриптор к текущему потоку.|  
|[CWinThread::m\_nThreadID](../Topic/CWinThread::m_nThreadID.md)|Идентификатор текущего потока.|  
|[CWinThread::m\_pActiveWnd](../Topic/CWinThread::m_pActiveWnd.md)|Указатель на главное окно контейнерного приложения, когда OLE\-сервер активный в\- размещения.|  
|[CWinThread::m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md)|Сохраняет указатель на главное окно приложения.|  
  
## Заметки  
 Главный поток выполнения обычно предоставляется объектом, производным от `CWinApp`; `CWinApp` является производным от `CWinThread`.  Дополнительные объекты `CWinThread` позволяют выполнять несколько потоков в пределах заданного приложения.  
  
 2 Часто используемыми типами потоков, которые `CWinThread` поддерживает: рабочие потоки и потоки интерфейса пользователя.  Рабочие потоки не имеют цикл обработки сообщений: например, поток, выполняющий вычисления фона в приложении электронных таблиц.  Потоки интерфейса пользователя есть сообщения насоса и процессов, полученные из системы.  [CWinApp](../../mfc/reference/cwinapp-class.md) и производные от него классы примерами потоков интерфейса пользователя.  Другие потоки интерфейса пользователя также может наследоваться напрямую от `CWinThread`.  
  
 Объекты класса `CWinThread` обычно существуют на длительность потока.  Если нужно изменить эти расширения функциональности, установите [m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md) к **FALSE**.  
  
 Класс `CWinThread` необходим, чтобы сделать ваши код и MFC полностью потокобезопасным.  Поток\- локальные данные, используемые платформой для сохранения данных о поток\- определенной управляются объектами `CWinThread`.  Зависимость по этой причине на `CWinThread` для обработки поток\- локальных данных, любой поток, который использует MFC должна быть создана MFC.  Например, поток, переданный функцией среды выполнения [\_beginthread, \_beginthreadex](../Topic/_beginthread,%20_beginthreadex.md) не может использовать API MFC.  
  
 Создание потока, вызов [AfxBeginThread](../Topic/AfxBeginThread.md).  2 Формы, в зависимости от того, нужно ли поток операций или интерфейса пользователя.  Если необходимо, чтобы поток интерфейса пользователя, передайте в `AfxBeginThread` указатель на `CRuntimeClass` вашего `CWinThread`\- производный класс.  Если нужно создать рабочий поток, передайте в `AfxBeginThread` указатель на функцию управления, и параметром функции контроля.  Для обоих рабочих потоков и потоков интерфейса пользователя, можно указать необязательные параметры, которые изменяют приоритет, размер стека, флаги создания и атрибуты безопасности.  `AfxBeginThread` возвращает указатель на новый объект `CWinThread`.  
  
 Вместо вызова `AfxBeginThread`, можно создать производный объект `CWinThread` а затем вызвать `CreateThread`.  Этот метод двухступенный конструкции полезен, если нужно повторно использовать объект `CWinThread` между последовательными создания и прекращениями запуска потока.  
  
 Дополнительные сведения о `CWinThread` см. в разделе статьи [многопоточность с C\+\+ и MFC](../../parallel/multithreading-with-cpp-and-mfc.md), [Многопоточность. Создание потоков интерфейса пользователя](../../parallel/multithreading-creating-user-interface-threads.md), [Многопоточность. Создание рабочих потоков](../../parallel/multithreading-creating-worker-threads.md) и [Многопоточность. Использование классов синхронизации](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CWinThread`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)