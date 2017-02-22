---
title: "CWinApp Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinApp"
  - "hInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application objects [C++]"
  - "CWinApp class"
  - "HINSTANCE"
  - "main object"
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CWinApp Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс, от которого наследуется объект windows\-приложения.  
  
## Синтаксис  
  
```  
class CWinApp : public CWinThread  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinApp::CWinApp](../Topic/CWinApp::CWinApp.md)|Создает объект `CWinApp`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinApp::AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)|Добавляет шаблон документов в список доступных шаблонов документов приложения.|  
|[CWinApp::AddToRecentFileList](../Topic/CWinApp::AddToRecentFileList.md)|Добавляет имя файла в последний использовавший ся список файлов \(MRU\).|  
|[CWinApp::ApplicationRecoveryCallback](../Topic/CWinApp::ApplicationRecoveryCallback.md)|Вызываемый платформой, когда приложение неожиданно ".|  
|[CWinApp::CloseAllDocuments](../Topic/CWinApp::CloseAllDocuments.md)|Закрывает все открытые документы.|  
|[CWinApp::CreatePrinterDC](../Topic/CWinApp::CreatePrinterDC.md)|Создает контекст устройства принтера.|  
|[CWinApp::DelRegTree](../Topic/CWinApp::DelRegTree.md)|Удаляет указанный ключ и все его подразделы.|  
|[CWinApp::DoMessageBox](../Topic/CWinApp::DoMessageBox.md)|Средства [AfxMessageBox](../Topic/AfxMessageBox.md) для приложения.|  
|[CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)|Преобразует курсор ожидания и состояние on.|  
|[CWinApp::EnableD2DSupport](../Topic/CWinApp::EnableD2DSupport.md)|Включает поддержку `D2D` приложения.  Этот метод следует вызывать перед инициализацией главного окна.|  
|[CWinApp::EnableHtmlHelp](../Topic/CWinApp::EnableHtmlHelp.md)|Средства HTMLHelp для приложения, а не WinHelp.|  
|[CWinApp::EnableTaskbarInteraction](../Topic/CWinApp::EnableTaskbarInteraction.md)|Включает взаимодействие панели задач.|  
|[CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md)|Переопределение для очистки когда приложение завершает.|  
|[CWinApp::GetApplicationRecoveryParameter](../Topic/CWinApp::GetApplicationRecoveryParameter.md)|Получает входной параметр для метода восстановления приложения.|  
|[CWinApp::GetApplicationRecoveryPingInterval](../Topic/CWinApp::GetApplicationRecoveryPingInterval.md)|Возвращает продолжительность времени, диспетчер перезапуска ожидает функции обратного вызова восстановления для возврата.|  
|[CWinApp::GetApplicationRestartFlags](../Topic/CWinApp::GetApplicationRestartFlags.md)|Возвращает флаги для диспетчера перезапуска.|  
|[CWinApp::GetAppRegistryKey](../Topic/CWinApp::GetAppRegistryKey.md)|Ключ для возвращений HKEY\_CURRENT\_USER\\"Software"\\RegistryKey\\ProfileName.|  
|[CWinApp::GetDataRecoveryHandler](../Topic/CWinApp::GetDataRecoveryHandler.md)|Получает обработчик восстановления данных для этого экземпляра приложения.|  
|[CWinApp::GetFirstDocTemplatePosition](../Topic/CWinApp::GetFirstDocTemplatePosition.md)|Получает положение первого шаблона документа.|  
|[CWinApp::GetHelpMode](../Topic/CWinApp::GetHelpMode.md)|Извлекает тип справки, используемый приложением.|  
|[CWinApp::GetNextDocTemplate](../Topic/CWinApp::GetNextDocTemplate.md)|Извлекает позицию шаблона документа.  Может использоваться рекурсивно.|  
|[CWinApp::GetPrinterDeviceDefaults](../Topic/CWinApp::GetPrinterDeviceDefaults.md)|Получает значения по умолчанию устройства принтера.|  
|[CWinApp::GetProfileBinary](../Topic/CWinApp::GetProfileBinary.md)|Получает двоичные данные из записи в ini\-файле приложения.|  
|[CWinApp::GetProfileInt](../Topic/CWinApp::GetProfileInt.md)|Извлекает целое число от записи в ini\-файле приложения.|  
|[CWinApp::GetProfileString](../Topic/CWinApp::GetProfileString.md)|Извлекает строку из записи в ini\-файле приложения.|  
|[CWinApp::GetSectionKey](../Topic/CWinApp::GetSectionKey.md)|Ключ для возвращений HKEY\_CURRENT\_USER\\"Software"\\RegistryKey\\AppName\\lpszSection.|  
|[CWinApp::HideApplication](../Topic/CWinApp::HideApplication.md)|Скрывает приложение перед закрыть все документы.|  
|[CWinApp::HtmlHelp](../Topic/CWinApp::HtmlHelp.md)|Вызывает функцию `HTMLHelp` Windows.|  
|[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md)|Переопределение для инициализации экземпляра Windows, как создать объекты окна.|  
|[CWinApp::IsTaskbarInteractionEnabled](../Topic/CWinApp::IsTaskbarInteractionEnabled.md)|Указывает, включено ли взаимодействие панели задач Windows 7.|  
|[CWinApp::LoadCursor](../Topic/CWinApp::LoadCursor.md)|Загружает ресурс курсора.|  
|[CWinApp::LoadIcon](../Topic/CWinApp::LoadIcon.md)|Загружает ресурс значка.|  
|[CWinApp::LoadOEMCursor](../Topic/CWinApp::LoadOEMCursor.md)|Загружает предварительно OEM курсор Windows, константы **OCR\_** определяют в WINDOWS.H.|  
|[CWinApp::LoadOEMIcon](../Topic/CWinApp::LoadOEMIcon.md)|Загружает предварительно OEM значок Windows, константы **OIC\_** определяют в WINDOWS.H.|  
|[CWinApp::LoadStandardCursor](../Topic/CWinApp::LoadStandardCursor.md)|Загружает курсор предопределенный Windows, константы **IDC\_** определяют в WINDOWS.H.|  
|[CWinApp::LoadStandardIcon](../Topic/CWinApp::LoadStandardIcon.md)|Загружает предварительно определенный значок Windows, константы **IDI\_** определяют в WINDOWS.H.|  
|[CWinApp::OnDDECommand](../Topic/CWinApp::OnDDECommand.md)|Вызываемый платформой в ответ на динамический обмен данными \(DDE\) выполните команду.|  
|[CWinApp::OnIdle](../Topic/CWinApp::OnIdle.md)|Переопределение выполнения зависит от приложения обработки времени простоя.|  
|[CWinApp::OpenDocumentFile](../Topic/CWinApp::OpenDocumentFile.md)|Вызываемый платформой для открытия документа из файла.|  
|[CWinApp::ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md)|Анализирует отдельные параметры и пометит в командной строке.|  
|[CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md)|Сообщения фильтров, прежде чем они отправляются в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](../Topic/CWinApp::ProcessMessageFilter.md)|Некоторые перехватывает сообщения до того, как они достигнут приложения.|  
|[CWinApp::ProcessShellCommand](../Topic/CWinApp::ProcessShellCommand.md)|Обрабатывает аргументы и флаги командной строки.|  
|[CWinApp::ProcessWndProcException](../Topic/CWinApp::ProcessWndProcException.md)|Перехватывает все необработанные исключения, вызываемые обработчиков сообщений и команды приложения.|  
|[CWinApp::Register](../Topic/CWinApp::Register.md)|Выполняет настраивал регистрацию.|  
|[CWinApp::RegisterWithRestartManager](../Topic/CWinApp::RegisterWithRestartManager.md)|Регистрирует приложение с помощью диспетчера перезапуска.|  
|[CWinApp::ReopenPreviousFilesAtRestart](../Topic/CWinApp::ReopenPreviousFilesAtRestart.md)|Определяет обнаруживает вновь ли диспетчер перезапуска файлы, которые были открытыми, когда приложение слева.|  
|[CWinApp::RestartInstance](../Topic/CWinApp::RestartInstance.md)|Обрабатывает перезапуску приложения, разработанного диспетчером перезапуска.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](../Topic/CWinApp::RestoreAutosavedFilesAtRestart.md)|Определяет, возвращает ли диспетчер перезапуска autosaved файлы, когда он перезапускает приложение.|  
|[CWinApp::Run](../Topic/CWinApp::Run.md)|По умолчанию выполняется цикл обработки сообщений.  Переопределение настраивать цикл обработки сообщений.|  
|[CWinApp::RunAutomated](../Topic/CWinApp::RunAutomated.md)|Проверяет командная строка приложения для параметра **\/Automation**.  Является устаревшей.  Вместо этого используйте значение в [CCommandLineInfo::m\_bRunAutomated](../Topic/CCommandLineInfo::m_bRunAutomated.md) после вызова [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::RunEmbedded](../Topic/CWinApp::RunEmbedded.md)|Проверяет командная строка приложения для параметра **\/Embedding**.  Является устаревшей.  Вместо этого используйте значение в [CCommandLineInfo::m\_bRunEmbedded](../Topic/CCommandLineInfo::m_bRunEmbedded.md) после вызова [ParseCommandLine](../Topic/CWinApp::ParseCommandLine.md).|  
|[CWinApp::SaveAllModified](../Topic/CWinApp::SaveAllModified.md)|Пользователю предлагается сохранить все измененные документы.|  
|[CWinApp::SelectPrinter](../Topic/CWinApp::SelectPrinter.md)|Выберите принтер, показанный ранее пользователем в диалоговом окне печать.|  
|[CWinApp::SetHelpMode](../Topic/CWinApp::SetHelpMode.md)|Наборы и инициализируют тип справки, используемый приложением.|  
|[CWinApp::SupportsApplicationRecovery](../Topic/CWinApp::SupportsApplicationRecovery.md)|Определяет восстанавливает ли диспетчер перезапуска приложения, слева.|  
|[CWinApp::SupportsAutosaveAtInterval](../Topic/CWinApp::SupportsAutosaveAtInterval.md)|Определяет autosaves ли диспетчер перезапуска открытые документы в регулярном интервале.|  
|[CWinApp::SupportsAutosaveAtRestart](../Topic/CWinApp::SupportsAutosaveAtRestart.md)|Определяет autosaves ли диспетчер перезапуска все открытые документы при перезапуске приложения.|  
|[CWinApp::SupportsRestartManager](../Topic/CWinApp::SupportsRestartManager.md)|Определяет, поддерживает ли приложение диспетчера перезапуска.|  
|[CWinApp::Unregister](../Topic/CWinApp::Unregister.md)|Отменяет регистрацию всех известное, что, зарегистрированные с объектом `CWinApp`.|  
|[CWinApp::WinHelp](../Topic/CWinApp::WinHelp.md)|Вызывает функцию `WinHelp` Windows.|  
|[CWinApp::WriteProfileBinary](../Topic/CWinApp::WriteProfileBinary.md)|Записывает двоичные данные для записи в ini\-файле приложения.|  
|[CWinApp::WriteProfileInt](../Topic/CWinApp::WriteProfileInt.md)|Записывает целое число для записи в ini\-файле приложения.|  
|[CWinApp::WriteProfileString](../Topic/CWinApp::WriteProfileString.md)|Записывает строку для записи в ini\-файле приложения.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinApp::EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md)|Позволяет пользователю открыть файлы данных из файлового менеджера Windows.|  
|[CWinApp::LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)|Загружает стандартные параметры ini\-файла и включает функцию списка файлов MRU.|  
|[CWinApp::OnContextHelp](../Topic/CWinApp::OnContextHelp.md)|Справка маркеров SHIFT\+F1 в приложении.|  
|[CWinApp::OnFileNew](../Topic/CWinApp::OnFileNew.md)|Реализует команду `ID_FILE_NEW`.|  
|[CWinApp::OnFileOpen](../Topic/CWinApp::OnFileOpen.md)|Реализует команду `ID_FILE_OPEN`.|  
|[CWinApp::OnFilePrintSetup](../Topic/CWinApp::OnFilePrintSetup.md)|Реализует команду `ID_FILE_PRINT_SETUP`.|  
|[CWinApp::OnHelp](../Topic/CWinApp::OnHelp.md)|Справка F1 маркеров в рамках приложения \(с использованием текущего контекста\).|  
|[CWinApp::OnHelpFinder](../Topic/CWinApp::OnHelpFinder.md)|Обрабатывает команды `ID_HELP_FINDER` и `ID_DEFAULT_HELP`.|  
|[CWinApp::OnHelpIndex](../Topic/CWinApp::OnHelpIndex.md)|Выполняет команду `ID_HELP_INDEX` и предоставляет по умолчанию раздел Справки.|  
|[CWinApp::OnHelpUsing](../Topic/CWinApp::OnHelpUsing.md)|Выполняет обработку команды `ID_HELP_USING`.|  
|[CWinApp::RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md)|Регистрирует типы документов все приложения с файловыми менеджером Windows.|  
|[CWinApp::SetAppID](../Topic/CWinApp::SetAppID.md)|Явно задает идентификатор модели пользователя приложения для приложения.  Этот метод должен быть вызван перед вызовом любой пользовательский интерфейс для пользователя \(лучшее место конструктор приложения\).|  
|[CWinApp::SetRegistryKey](../Topic/CWinApp::SetRegistryKey.md)|Указывает параметры приложения быть сохранены в реестре, а не файлы INI.|  
|[CWinApp::UnregisterShellFileTypes](../Topic/CWinApp::UnregisterShellFileTypes.md)|Отменяет регистрацию всех типов документов приложения с файловыми менеджером Windows.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinApp::m\_bHelpMode](../Topic/CWinApp::m_bHelpMode.md)|Показывает, если пользователь находится в режиме, то контекста Справки \(обычно призванном с SHIFT\+F1\).|  
|[CWinApp::m\_eHelpType](../Topic/CWinApp::m_eHelpType.md)|Указывает тип справки, используемый приложением.|  
|[CWinApp::m\_hInstance](../Topic/CWinApp::m_hInstance.md)|Определяет текущий экземпляр приложения.|  
|[CWinApp::m\_lpCmdLine](../Topic/CWinApp::m_lpCmdLine.md)|Указывает на null\- завершенной строке, которая задает командную строку для приложения.|  
|[CWinApp::m\_nCmdShow](../Topic/CWinApp::m_nCmdShow.md)|Определяет, как окно отображаться исходная.|  
|[CWinApp::m\_pActiveWnd](../Topic/CWinApp::m_pActiveWnd.md)|Указатель на главное окно контейнерного приложения, когда OLE\-сервер активный в\- размещения.|  
|[CWinApp::m\_pszAppID](../Topic/CWinApp::m_pszAppID.md)|Идентификатор модели. пользователя приложения|  
|[CWinApp::m\_pszAppName](../Topic/CWinApp::m_pszAppName.md)|Указывает имя приложения.|  
|[CWinApp::m\_pszExeName](../Topic/CWinApp::m_pszExeName.md)|Имя модуля приложения.|  
|[CWinApp::m\_pszHelpFilePath](../Topic/CWinApp::m_pszHelpFilePath.md)|Путь к файлу Справки приложения.|  
|[CWinApp::m\_pszProfileName](../Topic/CWinApp::m_pszProfileName.md)|Имя файла INI приложения.|  
|[CWinApp::m\_pszRegistryKey](../Topic/CWinApp::m_pszRegistryKey.md)|Используемый, чтобы определить полный раздел реестра для хранения параметров профиля приложения.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinApp::m\_dwRestartManagerSupportFlags](../Topic/CWinApp::m_dwRestartManagerSupportFlags.md)|Пометит, определяющее, как диспетчер перезапуска будет работать.|  
|[CWinApp::m\_nAutosaveInterval](../Topic/CWinApp::m_nAutosaveInterval.md)|Время \(в миллисекундах autosaves.|  
|[CWinApp::m\_pDataRecoveryHandler](../Topic/CWinApp::m_pDataRecoveryHandler.md)|Указатель на обработчик восстановления данных для приложения.|  
  
## Заметки  
 Объект приложения предоставляет функции\-члены для инициализации приложения \(а каждый его экземпляр\) для запуска приложения.  
  
 Каждое приложение, которое использует классы Microsoft foundation может содержать только один объект, производный от `CWinApp`.  Этот объект создается, когда другие глобальные объекты C\+\+ строятся и уже доступен, когда Windows вызывает функцию `WinMain`, которая предоставляется библиотеки Microsoft Foundation Class.  Объявите производный объект `CWinApp` на глобальном уровне.  
  
 При наследовании класса приложения из `CWinApp`, следует переопределить функцию\-член [InitInstance](../Topic/CWinApp::InitInstance.md) для создания объекта основного окна приложения.  
  
 В дополнение к функции\-членам `CWinApp`, библиотеки Microsoft Foundation Class предоставляет следующие глобальные функции для получения доступа к объект `CWinApp` и другие глобальные сведения:  
  
-   [AfxGetApp](../Topic/AfxGetApp.md) получает указатель на объект `CWinApp`.  
  
-   [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) получает дескриптор для текущего экземпляра приложения.  
  
-   [AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md) получает дескриптор к ресурсам приложения.  
  
-   [AfxGetAppName](../Topic/AfxGetAppName.md) получает указатель на строку, содержащую имя приложения.  Кроме того, если имеется указатель на объект `CWinApp`, используйте `m_pszExeName` чтобы получить имя приложения.  
  
 См. раздел [CWinApp: класс приложения](../Topic/CWinApp:%20The%20Application%20Class.md) дополнительные сведения о классе `CWinApp`, включая описание следующих действий:  
  
-   Производный `CWinApp` код, написанный мастером настройки приложений.  
  
-   Роль `CWinApp` в последовательности выполнения приложения.  
  
-   Реализации функции элемента по умолчанию `CWinApp`.  
  
-   Переопределяемые методы `CWinApp` ключевые.  
  
 Элемент данных **m\_hPrevInstance** больше не существует.  Дополнительные сведения о обнаружить предыдущий экземпляр `CWinApp` см. в статье базы знаний "указывающее предыдущий экземпляр приложения" \(KB106385\) [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;106385](http://support.microsoft.com/default.aspx?scid=kb;en-us;106385).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CWinThread Class](../../mfc/reference/cwinthread-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)