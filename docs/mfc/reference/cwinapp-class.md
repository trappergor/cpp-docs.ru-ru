---
title: Класс CWinApp
ms.date: 11/04/2016
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: 6366638ebfd5e78ad517a8913e4276d5cd820670
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264682"
---
# <a name="cwinapp-class"></a>Класс CWinApp

Базовый класс, от которого необходимо наследовать объект приложения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CWinApp::CWinApp](#cwinapp)|Создает объект `CWinApp`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp::AddDocTemplate](#adddoctemplate)|Добавляет шаблон документа список шаблонов документов, доступных в приложения.|
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Добавляет имя файла в списке недавно использованных файлов (MRU).|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Вызывается платформой, когда приложение неожиданно завершает работу.|
|[CWinApp::CloseAllDocuments](#closealldocuments)|Закрывает все открытые документы.|
|[CWinApp::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера.|
|[CWinApp::DelRegTree](#delregtree)|Удаляет указанный ключ и все его подразделы.|
|[CWinApp::DoMessageBox](#domessagebox)|Реализует [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для приложения.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|Включение и отключение, включение курсор ожидания.|
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Включает поддержку приложением D2D. Данный метод следует вызывать до инициализации основного окна.|
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Реализует HTMLHelp для приложения, а не WinHelp.|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Разрешает взаимодействие панели задач.|
|[CWinApp::ExitInstance](#exitinstance)|Переопределение для очистки, когда приложение завершает работу.|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Получает входной параметр для метода восстановления приложения.|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Возвращает продолжительность времени ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Возвращает флаги для диспетчера перезапуска.|
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\ProfileName «Программное обеспечение».|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Получает обработчик восстановления данных для этого экземпляра приложения.|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Возвращает позицию первого шаблона документа.|
|[CWinApp::GetHelpMode](#gethelpmode)|Извлекает тип справки, используемый приложением.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Получает положение шаблон документа. Можно рекурсивно использовать.|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Получает устройство по умолчанию.|
|[CWinApp::GetProfileBinary](#getprofilebinary)|Извлекает двоичные данные из записи в приложения. INI-файл.|
|[CWinApp::GetProfileInt](#getprofileint)|Возвращает целое число из элемента в приложения. INI-файл.|
|[CWinApp::GetProfileString](#getprofilestring)|Извлекает строку из элемента в приложения. INI-файл.|
|[CWinApp::GetSectionKey](#getsectionkey)|Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection «Программное обеспечение».|
|[CWinApp::HideApplication](#hideapplication)|Скрывает приложение перед тем как закрыть все документы.|
|[CWinApp::HtmlHelp](#htmlhelp)|Вызовы `HTMLHelp` функции Windows.|
|[CWinApp::InitInstance](#initinstance)|Переопределите, чтобы выполнить инициализацию экземпляра Windows, таких как создание объектов окна.|
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Указывает, включена ли взаимодействия на панели задач Windows 7.|
|[CWinApp::LoadCursor](#loadcursor)|Загружает ресурс курсора.|
|[CWinApp::LoadIcon](#loadicon)|Загружает ресурс значка.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Загружает Windows OEM предопределенные курсора, **OCR_** константы указывают в WINDOWS. З.|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Загружает значок в виде стандартных Windows OEM, **OIC_** константы указывают в WINDOWS. З.|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Загружает Windows предопределенные курсора, **IDC_** константы указывают в WINDOWS. З.|
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Загружает предварительно определенных значком Windows, **IDI_** константы указывают в WINDOWS. З.|
|[CWinApp::OnDDECommand](#onddecommand)|Вызывается платформой динамических данных exchange (DDE) выполните команду.|
|[CWinApp::OnIdle](#onidle)|Переопределение для выполнения обработки времени простоя приложения.|
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Вызывается платформой для открытия документа из файла.|
|[CWinApp::ParseCommandLine](#parsecommandline)|Выполняет синтаксический анализ отдельных параметров и флагов в командной строке.|
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Фильтрует сообщения перед их отправкой в функции Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенных сообщений, прежде чем они достигнут приложения.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|Обрабатывает аргументы командной строки и флаги.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, порождаемые сообщения приложения и обработчиков команд.|
|[CWinApp::Register](#register)|Выполняет настраиваемые регистрацию.|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Регистрирует приложение с диспетчером перезапуска.|
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Определяет, открывается ли диспетчер перезапуска повторно файлы, которые были открыты, когда приложение неожиданно.|
|[CWinApp::RestartInstance](#restartinstance)|Обрабатывает инициированным диспетчером перезапуска перезапуска приложения.|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Определяет, восстанавливает ли диспетчер перезапуска автоматическое сохранение файлов после его перезапуска приложения.|
|[CWinApp::Run](#run)|Запускает цикл обработки сообщений по умолчанию. Переопределения, чтобы настроить цикл обработки сообщений.|
|[CWinApp::RunAutomated](#runautomated)|Проверяет приложения командной строки для **/Automation** параметр. Является устаревшей. Вместо этого используйте значение в [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) после вызова метода [ParseCommandLine](#parsecommandline).|
|[CWinApp::RunEmbedded](#runembedded)|Проверяет приложения командной строки для **/Embedding** параметр. Является устаревшей. Вместо этого используйте значение в [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) после вызова метода [ParseCommandLine](#parsecommandline).|
|[CWinApp::SaveAllModified](#saveallmodified)|Предлагает пользователю сохранить все измененные документы.|
|[CWinApp::SelectPrinter](#selectprinter)|Служит для выбора принтера, ранее определено пользователем через диалоговое окно печати.|
|[CWinApp::SetHelpMode](#sethelpmode)|Задает и инициализирует тип справки, используемый приложением.|
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Определяет, восстановилось ли диспетчер перезапуска приложения, которое неожиданно завершил работу.|
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Определяет, ли преждевременном прекращении работы диспетчера перезапуска открывать документы с регулярным интервалом.|
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Определяет, является ли преждевременном прекращении работы диспетчера перезапуска открытые документы при повторном запуске приложения.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Определяет, поддерживает ли приложение диспетчера перезапуска.|
|[CWinApp::Unregister](#unregister)|Отменяет регистрацию всеми сведениями, чтобы зарегистрировать с `CWinApp` объекта.|
|[CWinApp::WinHelp](#winhelp)|Вызовы `WinHelp` функции Windows.|
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Записывает двоичные данные для записи в приложения. INI-файл.|
|[CWinApp::WriteProfileInt](#writeprofileint)|Записывает целое число для записи в приложения. INI-файл.|
|[CWinApp::WriteProfileString](#writeprofilestring)|Записывает строку в запись в приложения. INI-файл.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp::EnableShellOpen](#enableshellopen)|Позволяет пользователю открывать файлы данных в диспетчере файлов Windows.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Загружает standard. Параметры INI-файла и включает MRU файла списка компонентов.|
|[CWinApp::OnContextHelp](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 справки в приложении.|
|[CWinApp::OnFileNew](#onfilenew)|Реализует id_file_new-команда.|
|[CWinApp::OnFileOpen](#onfileopen)|Реализует id_file_open-команда.|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Реализует id_file_print_setup-команда.|
|[CWinApp::OnHelp](#onhelp)|Обрабатывает справку F1 в приложении (с использованием текущего контекста).|
|[CWinApp::OnHelpFinder](#onhelpfinder)|Обрабатывает команды ID_HELP_FINDER и ID_DEFAULT_HELP.|
|[CWinApp::OnHelpIndex](#onhelpindex)|Id_help_index-команда обрабатывает и предоставляет раздел справки по умолчанию.|
|[CWinApp::OnHelpUsing](#onhelpusing)|Обрабатывает id_help_using-команда.|
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|Регистрирует типов документов приложения с помощью диспетчера файлов Windows.|
|[CWinApp::SetAppID](#setappid)|Явно задает идентификатор модели пользователя приложения для приложения. Этот метод должен вызываться до никакого пользовательского интерфейса отображаются для пользователя (лучше всего — это конструктор приложения).|
|[CWinApp::SetRegistryKey](#setregistrykey)|Параметры приложения для сохранения в реестре, а не в результате. INI-файлы.|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Отменяет регистрацию типов документов приложения с помощью диспетчера файлов Windows.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Указывает, является ли пользователь режим контекста справки (обычно вызывается с помощью клавиши SHIFT + F1).|
|[CWinApp::m_eHelpType](#m_ehelptype)|Указывает тип справки, используемый приложением.|
|[CWinApp::m_hInstance](#m_hinstance)|Определяет текущий экземпляр приложения.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Указатель на заканчивающуюся нулем строку, указывающую командной строки для приложения.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Определяет, как будет первоначально отображаться окно.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера при OLE-сервер активен на месте.|
|[CWinApp::m_pszAppID](#m_pszappid)|Идентификатор модели пользователя приложения.|
|[CWinApp::m_pszAppName](#m_pszappname)|Указывает имя приложения.|
|[CWinApp::m_pszExeName](#m_pszexename)|Имя модуля приложения.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Путь к файлу справки приложения.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Приложения. Имя INI-файла.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Используется для определения полного реестра для хранения параметров профиля приложения.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Флаги, которые определяют поведение диспетчера перезапуска.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Продолжительность времени в миллисекундах между преждевременном прекращении работы.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Указатель на обработчик восстановления данных для приложения.|

## <a name="remarks"></a>Примечания

Объект приложения предоставляет функции-члены для инициализации приложения (и каждого экземпляра), а также для запуска приложения.

Каждое приложение, использующее классы Microsoft Foundation может содержать только один объект, производный от `CWinApp`. Этот объект создается при создании других глобальных объектов C++ и уже доступна, когда Windows вызывает `WinMain` функцию, которая предоставляется свойством библиотеки Microsoft Foundation Class. Объявите в производный `CWinApp` объекта на глобальном уровне.

При наследовании классу приложения из `CWinApp`, переопределить [InitInstance](#initinstance) функция-член для создания объекта главного окна приложения.

В дополнение к `CWinApp` функций-членов библиотеки Microsoft Foundation Class предоставляет следующие глобальные функции для доступа к вашей `CWinApp` объекта и другие глобальные сведения:

- [AfxGetApp](application-information-and-management.md#afxgetapp) получает указатель на `CWinApp` объект.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Получает дескриптор текущего экземпляра приложения.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Получает дескриптор к ресурсам приложения.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) получает указатель на строку, содержащую имя приложения. Кроме того Если у вас есть указатель на `CWinApp` , используйте `m_pszExeName` для получения имени приложения.

См. в разделе [CWinApp: Класс приложения](../../mfc/cwinapp-the-application-class.md) дополнительную информацию о `CWinApp` класса, включая общие сведения о следующих:

- `CWinApp`-производные код, написанный с помощью мастера приложений.

- `CWinApp`в роли в последовательность выполнения приложения.

- `CWinApp`в реализациях функций-членов по умолчанию.

- `CWinApp`в ключа переопределяются.

`m_hPrevInstance` Элемент данных больше не существует. Чтобы определить, выполняется ли другой экземпляр приложения, используйте именованного мьютекса. Если не удается открыть мьютекс, отсутствуют другие экземпляры приложения, запущенного.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="adddoctemplate"></a>  CWinApp::AddDocTemplate

Вызывайте эту функцию элемента для добавления шаблона документа в список шаблонов доступных документов, которые поддерживает приложение.

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Параметры

*pTemplate*<br/>
Указатель на `CDocTemplate` для добавления.

### <a name="remarks"></a>Примечания

Следует добавить все шаблоны в приложение документов, перед вызовом метода [RegisterShellFileTypes](#registershellfiletypes).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList

Вызывайте эту функцию члена, чтобы добавить *lpszPathName* в список последних Выбиравшихся файлов.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Путь к файлу.

### <a name="remarks"></a>Примечания

Следует вызывать [LoadStdProfileSettings](#loadstdprofilesettings) функция-член для загрузки текущий список файлов, прежде чем использовать эту функцию-член.

Эта функция-член вызывается платформой, когда он открывает файл, или выполняет команду Сохранить как, чтобы сохранить файл с новым именем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback

Вызывается платформой, когда приложение неожиданно завершает работу.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Параметры

*lpvParam*<br/>
[in] Зарезервировано для будущего использования.

### <a name="return-value"></a>Возвращаемое значение

0, если этот метод выполнен успешно; ненулевое значение, если произошла ошибка.

### <a name="remarks"></a>Примечания

Если приложение поддерживает диспетчер перезапуска, платформа вызывает эту функцию, когда приложение неожиданно завершает работу.

Реализация по умолчанию `ApplicationRecoveryCallback` использует `CDataRecoveryHandler` сохранить список открытых документов в реестр. Этот метод не выполняет автосохранения не все файлы.

Для настройки поведения, переопределите эту функцию в производном [класс CWinApp](../../mfc/reference/cwinapp-class.md) или передать свой собственный метод восстановления приложения в качестве параметра [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments

Вызов этой функции-члена для закрытие всех открытых документов перед завершением работы.

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Параметры

*bEndSession*<br/>
Указывает, выполняется ли окончания сеанса Windows. Он имеет значение TRUE, если сеанс завершен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызовите [HideApplication](#hideapplication) перед вызовом `CloseAllDocuments`.

##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC

Вызов этой функции-члена для создания контекста принтера устройства (DC) из выбранного принтера.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Параметры

*dc*<br/>
Ссылка на контекст устройства принтера.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если контекст устройства принтера создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

`CreatePrinterDC` Инициализирует контекст устройства, которое передается по ссылке, чтобы можно было использовать для печати.

Если функция выполнена успешно, когда вы закончите печати, вы должны уничтожить контекст устройства. Вы можете разрешить деструктор класса [CDC](../../mfc/reference/cdc-class.md) объект выполняет его, или это можно сделать явно, вызвав [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).

##  <a name="cwinapp"></a>  CWinApp::CWinApp

Создает `CWinApp` объект и передает *lpszAppName* должен храниться как имя приложения.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszAppName*<br/>
Завершающаяся нулем строка, содержащая имя приложения, использующего Windows. Если этот аргумент не задан или имеет значение NULL, `CWinApp` использует строку ресурса AFX_IDS_APP_TITLE или имя исполняемого файла.

### <a name="remarks"></a>Примечания

Необходимо так сконструировать один глобальный объект вашей `CWinApp`-производного класса. Может иметь только один `CWinApp` объекта в приложении. Конструктор сохраняет указатель на `CWinApp` объекта, чтобы `WinMain` можно вызвать объекта функции-члены для инициализации и запуска приложения.

##  <a name="delregtree"></a>  CWinApp::DelRegTree

Удаляет раздел реестра и все его подразделы.

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*hParentKey*<br/>
Дескриптор раздела реестра.

*strKeyName*<br/>
Имя раздела реестра для удаления.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевого значения ошибки, определенный в Winerror.h.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы удалить указанные ключ и его подразделы.

##  <a name="domessagebox"></a>  CWinApp::DoMessageBox

Платформа вызывает эту функцию-член для реализации окно сообщения для глобальной функции [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Параметры

*lpszPrompt*<br/>
Адрес текста в окне сообщения.

*nType*<br/>
В окне сообщения [стиля](../../mfc/reference/styles-used-by-mfc.md#message-box-styles).

*nIDPrompt*<br/>
Индекс для строки контекста справки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает те же значения, что `AfxMessageBox`.

### <a name="remarks"></a>Примечания

Не вызывайте эта функция-член для окна сообщения; Используйте `AfxMessageBox` вместо этого.

Переопределите эту функцию-член для настройки на уровне приложения обработки `AfxMessageBox` вызовов.

##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor

Эта функция-член вызывается платформой для реализации [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), и [ CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Параметры

*nCode*<br/>
Если этот параметр равен 1, отображается курсор ожидания. Если значение равно 0, курсор ожидания восстанавливается без приращения счетчика ссылок. Если значение-1, завершает курсор ожидания.

### <a name="remarks"></a>Примечания

Значение по умолчанию реализует курсор с песочными часами. `DoWaitCursor` поддерживает счетчик ссылок. Когда положительно, отображается курсор с песочными часами.

Хотя вы обычно не вызывается `DoWaitCursor` напрямую, можно переопределить эту функцию-член для изменения курсор ожидания или выполнять дополнительную обработку, когда отображается курсор ожидания.

Это проще и более простой способ реализовать курсор ожидания, используйте `CWaitCursor`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Включает поддержку приложением D2D. Данный метод следует вызывать до инициализации основного окна.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Параметры

*d2dFactoryType*<br/>
Потоковая модель фабрики D2D и ресурсы, которые он создает.

*writeFactoryType*<br/>
Значение, указывающее, будет ли объект фабрики записи совместно или изолированной

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если поддержка D2D был включен, FALSE — в противном случае

##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp

Вызовите эту функцию-член из конструктора вашей `CWinApp`-производный класс использовать для получения справки приложения HTMLHelp.

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Примечания

##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen

Вызывайте эту функцию, обычно из вашей `InitInstance` переопределение, чтобы пользователи приложения могли открывать файлы данных, после двойного щелчка в диспетчере файлов Windows файлы из.

```
void EnableShellOpen();
```

### <a name="remarks"></a>Примечания

Вызовите `RegisterShellFileTypes` член функции в сочетании с помощью этой функции или предоставить. REG-файл вместе с приложением для ручной регистрации типов документов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction

Разрешает взаимодействие панели задач.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Определяет, должен быть включен (TRUE) взаимодействие с панели задач Windows 7, или выключен (FALSE).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если взаимодействие задач может быть включен или отключен.

### <a name="remarks"></a>Примечания

Этот метод должен вызываться до создания главного окна, в противном случае он утверждает и возвращает значение FALSE.

##  <a name="exitinstance"></a>  CWinApp::ExitInstance

Вызывается платформой изнутри `Run` функцию-член для выхода из этого экземпляра приложения.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Код выхода приложения; 0 указывает без ошибок, а значения больше 0 указывает на ошибку. Это значение используется как возвращаемое значение из `WinMain`.

### <a name="remarks"></a>Примечания

Не вызывайте эту функцию-член из любого места но в `Run` функция-член.

Реализация по умолчанию эта функция записывает параметры framework приложения. INI-файл. Переопределите эту функцию для очистки, когда приложение завершает работу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter

Получает входной параметр для метода восстановления приложения.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Возвращаемое значение

Входного параметра по умолчанию для метода восстановления приложения.

### <a name="remarks"></a>Примечания

По умолчанию эта функция возвращает значение NULL.

Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval

Возвращает продолжительность времени ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность времени в миллисекундах.

### <a name="remarks"></a>Примечания

Когда приложение, в которой зарегистрирован неожиданно завершает работу диспетчера перезапуска, приложение пытается сохранить открытые документы и вызывает функцию обратного вызова для восстановления. Функция обратного вызова для восстановления по умолчанию является [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

Продолжительность времени, платформа ожидает возврата данных функцией обратного вызова восстановления является интервал проверки связи. Вы можете настроить интервал проверки связи, переопределяя `CWinApp::GetApplicationRecoveryPingInterval` или предоставив пользовательское значение для `RegisterWithRestartManager`.

##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags

Возвращает флаги для диспетчера перезапуска.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Возвращаемое значение

Флаги для диспетчера перезапуска. Реализация по умолчанию возвращает значение 0.

### <a name="remarks"></a>Примечания

Флаги для диспетчера перезапуска не оказывают влияния реализацией по умолчанию. Они предназначены для использования в будущем.

Задать флажки при регистрации приложения с диспетчером перезапуска с помощью [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

Далее приведены возможные значения для флагов диспетчер перезапуска.

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey

Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\ProfileName «Программное обеспечение».

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ приложения, если функция выполнилась успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler

Получает обработчик восстановления данных для этого экземпляра приложения.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик восстановления данных для этого экземпляра приложения.

### <a name="remarks"></a>Примечания

Каждое приложение, который использует диспетчер перезапуска необходимо иметь один экземпляр [класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md). Этот класс отвечает за мониторинг открытых документов и автоматическое сохранение файлов. Поведение `CDataRecoveryHandler` зависит от конфигурации диспетчера перезапуска. Дополнительные сведения см. в разделе [класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md).

Этот метод возвращает значение NULL в операционных системах более ранних, чем Windows Vista. Диспетчер перезапуска не поддерживается в операционных системах более ранних, чем Windows Vista.

Если приложение не имеет в данный момент обработчик восстановления данных, этот метод создает его и возвращает указатель на него.

##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition

Получает положение первого шаблона документа в приложении.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если список пуст.

### <a name="remarks"></a>Примечания

Используйте возвращаемое значение ПОЗИЦИИ в вызове [GetNextDocTemplate](#getnextdoctemplate) для получения первого [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объекта.

##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode

Извлекает тип справки, используемый приложением.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Возвращаемое значение

Тип справки, используемый приложением. См. в разделе [CWinApp::m_eHelpType](#m_ehelptype) Дополнительные сведения.

##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate

Получает шаблон документа, определяемый по *pos*, затем задает *pos* значение ПОЗИЦИИ.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Ссылку на ПОЗИЦИЮ, возвращенное предыдущим вызовом `GetNextDocTemplate` или [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Значение обновляется до следующей позиции этим вызовом.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объекта.

### <a name="remarks"></a>Примечания

Можно использовать `GetNextDocTemplate` в цикле прямой итерации, если установить начальное положение, с помощью вызова `GetFirstDocTemplatePosition`.

Необходимо убедиться, что значение ПОЗИЦИИ является допустимым. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Если шаблон полученного документа был последним доступно, выберите новое значение *pos* имеет значение NULL.

##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults

Вызовите эту функцию-член для подготовки контекст устройства принтера для печати.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Параметры

*pPrintDlg*<br/>
Указатель на [PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda) структуры.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Извлекает текущий по умолчанию из Windows. INI-файл как необходимые или использует последней конфигурации принтера, заданных пользователем в параметры печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>  CWinApp::GetProfileBinary

Вызовите эту функцию-член для получения двоичных данных из записи в указанный раздел реестра приложения или. INI-файл.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий элемент, значение которого равно требуется получить.

*ppData*<br/>
Указывает указатель, который будет получать адрес данных.

*pBytes*<br/>
Указывает целое число без знака, который будет принимать размер данных (в байтах).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член не должен учитываться регистр, поэтому строки в *lpszSection* и *lpszEntry* параметры отличаться только регистром.

> [!NOTE]
> `GetProfileBinary` выделяет буфер и возвращает его адрес в \* *ppData*. Вызывающий объект отвечает за освобождение буфера с помощью **delete []**.

> [!IMPORTANT]
> Данные, возвращаемые этой функцией не обязательно NULL завершается, и вызывающий объект должен выполнять проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Дополнительный пример см. в разделе [CWinApp::WriteProfileBinary](#writeprofilebinary).

##  <a name="getprofileint"></a>  CWinApp::GetProfileInt

Вызовите эту функцию-член для извлечения значения целого числа из записи в указанный раздел реестра приложения или. INI-файл.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий элемент, значение которого равно требуется получить.

*nDefault*<br/>
Задает значение по умолчанию для возврата, если платформа не найдена запись.

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение строки, которая следует за указанную запись, если функция выполнена успешно. Возвращается значение *nDefault* параметр, если функцию не удается найти запись. Возвращаемое значение равно 0, если значение, соответствующее в указанный элемент не является целым числом.

Эта функция-член поддерживает шестнадцатеричного формата для значения в. INI-файл. При извлечении целое число со знаком, следует привести значение в **int**.

### <a name="remarks"></a>Примечания

Эта функция-член не должен учитываться регистр, поэтому строки в *lpszSection* и *lpszEntry* параметры отличаться только регистром.

> [!IMPORTANT]
> Данные, возвращаемые этой функцией не обязательно NULL завершается, и вызывающий объект должен выполнять проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Дополнительный пример см. в разделе [CWinApp::WriteProfileInt](#writeprofileint).

##  <a name="getprofilestring"></a>  CWinApp::GetProfileString

Вызовите эту функцию-член для извлечения строки, связанной с записью в указанный раздел в реестре приложения или. INI-файл.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий записи, строка которого имеет требуется получить. Это значение не должно быть значение NULL.

*lpszDefault*<br/>
Указывает строковое значение по умолчанию для определенной записи, если элемент не найден в файле настройки.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение — это строка, из приложения. INI-файл или *lpszDefault* Если строка не найдена. Максимальная длина строки поддерживается платформой — _MAX_PATH. Если *lpszDefault* имеет значение NULL, возвращаемое значение является пустой строкой.

### <a name="remarks"></a>Примечания

> [!IMPORTANT]
> Данные, возвращаемые этой функцией не обязательно NULL завершается, и вызывающий объект должен выполнять проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример, см. в примере [CWinApp::GetProfileInt](#getprofileint).

##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey

Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection «Программное обеспечение».

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Имя ключа может быть получена.

*pTM*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ раздела, если функция выполнилась успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

##  <a name="hideapplication"></a>  CWinApp::HideApplication

Вызовите эту функцию-член скрытое приложение перед закрытием открытых документов.

```
void HideApplication();
```

##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp

Вызов этой функции-члена для вызова приложения HTMLHelp.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Параметры

*dwData*<br/>
Указывает дополнительные данные. Значение, используемое зависит от значения *nCmd* параметра.

*nCmd*<br/>
Задает тип запрошенной справки. Список возможных значений и как они влияют на *dwData* параметр, см. в разделе *uCommand* параметров, описанных в о HTMLHelp API функции в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Кроме того, платформа вызывает эту функцию для вызова приложения HTMLHelp.

Платформа автоматически закроет приложения HTMLHelp, когда приложение завершает работу.

##  <a name="initinstance"></a>  CWinApp::InitInstance

Windows позволяет несколько копий одной и той же программе для запуска в то же время.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Концептуально инициализации приложения состоит из двух разделов: инициализации одноразовый приложения, которая выполняется в первый раз программа запускается, а инициализацию экземпляра, который выполняется каждый раз копии программа запускается в том числе в первый раз. Реализация платформы `WinMain` вызывает эту функцию.

Переопределить `InitInstance` для инициализации каждого нового экземпляра приложения под управлением Windows. Как правило, можно переопределить `InitInstance` для создания объекта главного окна и задания `CWinThread::m_pMainWnd` данные-член для указания этого окна. Дополнительные сведения о переопределении эта функция-член, см. в разделе [CWinApp: Класс приложения](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> MFC-приложения должны инициализироваться как однопотоковое подразделение (STA). При вызове метода [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) в вашей `InitInstance` переопределения, укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled

Указывает, включена ли взаимодействия на панели задач Windows 7.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если `EnableTaskbarInteraction` был вызван и операционной системой является Windows 7 или более поздней версии.

### <a name="remarks"></a>Примечания

Задач взаимодействия означает, что MDI-приложения отображает содержимое элемента дочерние формы MDI в отдельные эскизы на вкладках, которые отображаются, когда указатель мыши находится на кнопке панели задач приложения.

##  <a name="loadcursor"></a>  CWinApp::LoadCursor

Загружает ресурс курсор с именем, *lpszResourceName* или определяется *nIDResource* из текущего исполняемого файла.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя ресурса курсора. Можно использовать `CString` для этого аргумента.

*nIDResource*<br/>
Идентификатор ресурса курсора. Список ресурсов, см. в разделе [LoadCursor](/windows/desktop/api/winuser/nf-winuser-loadcursora) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

`LoadCursor` Загружает курсора в памяти только в том случае, если он еще не был загружен ранее; в противном случае он извлекает дескриптор существующего ресурса.

Используйте [LoadStandardCursor](#loadstandardcursor) или [LoadOEMCursor](#loadoemcursor) функции-члена для доступа к предопределенные курсорами Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>  CWinApp::LoadIcon

Загружает ресурс значка с именем, *lpszResourceName* или определяется *nIDResource* из исполняемого файла.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя ресурса значка. Можно также использовать `CString` для этого аргумента.

*nIDResource*<br/>
Идентификатор ресурса значка.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для значка, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

`LoadIcon` загружает значок только в том случае, если он еще не был загружен ранее; в противном случае он извлекает дескриптор существующего ресурса.

Можно использовать [LoadStandardIcon](#loadstandardicon) или [LoadOEMIcon](#loadoemicon) функции-члена для доступа к предварительно определенных значков Windows.

> [!NOTE]
> Эта функция-член вызывает функцию Win32 API [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona), который может загружать только значок, размер которого соответствует значения метрик системы SM_CXICON и SM_CYICON.

##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor

Загружает Windows предопределенные курсора ресурс, заданный параметром *nIDCursor*.

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Параметры

*nIDCursor*<br/>
**OCR_** манифеста идентификатор константы, указывающее предопределенные курсора Windows. Необходимо иметь `#define OEMRESOURCE` перед `#include \<afxwin.h>` для получения доступа к **OCR_** константы в WINDOWS. З.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadOEMCursor` или [LoadStandardCursor](#loadstandardcursor) функции-члена для доступа к предопределенные курсорами Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon

Загружает Windows предопределенные значок ресурс, заданный параметром *nIDIcon*.

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Параметры

*nIDIcon*<br/>
**OIC_** манифеста идентификатор константы, указывающее предопределенные значок Windows. Необходимо иметь `#define OEMRESOURCE` перед `#include \<afxwin.h>` для доступа к **OIC_** константы в WINDOWS. З.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для значка, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadOEMIcon` или [LoadStandardIcon](#loadstandardicon) функции-члена для доступа к предварительно определенных значков Windows.

##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor

Загружает Windows предопределенные ресурса курсора, *lpszCursorName* указывает.

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Параметры

*lpszCursorName*<br/>
**IDC_** манифеста идентификатор константы, указывающее предопределенные курсора Windows. Эти идентификаторы определяются в WINDOWS. З. В следующем списке приведены возможные предопределенные значения и значения для *lpszCursorName*:

- IDC_ARROW стандартный курсор в виде стрелки

- IDC_IBEAM стандартный курсор Вставка текста

- Песочные часы IDC_WAIT курсор, используемый, когда Windows выполняет много времени

- IDC_CROSS перекрестия курсор для выделения

- IDC_UPARROW стрелку, указывающую вверх

- IDC_SIZE устаревшие и неподдерживаемые; использовать IDC_SIZEALL

- IDC_SIZEALL объект четырехконечная стрелка. Курсор изменения размера окна.

- IDC_ICON устаревшие и неподдерживаемые. Используйте IDC_ARROW.

- IDC_SIZENWSE двусторонней стрелки с интерфейсами в левом верхнем углу и в нижнем правом

- IDC_SIZENESW двусторонней стрелки с интерфейсами в верхнем левом углу справа и ниже

- Горизонтальная IDC_SIZEWE двусторонней стрелки

- Вертикальная IDC_SIZENS двусторонней стрелки

### <a name="return-value"></a>Возвращаемое значение

Дескриптор курсора, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadStandardCursor` или [LoadOEMCursor](#loadoemcursor) функции-члена для доступа к предопределенные курсорами Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon

Загружает Windows предопределенные ресурс значка, *lpszIconName* указывает.

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Параметры

*lpszIconName*<br/>
Манифеста идентификатор константы, указывающее предопределенные значок Windows. Эти идентификаторы определяются в WINDOWS. З. Список возможных стандартных значений и их описания, см. в разделе *lpIconName* параметр в [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona) в пакете Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Дескриптор для значка, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

Используйте `LoadStandardIcon` или [LoadOEMIcon](#loadoemicon) функции-члена для доступа к предварительно определенных значков Windows.

##  <a name="loadstdprofilesettings"></a>  CWinApp::LoadStdProfileSettings

Вызывает эту функцию-член из [InitInstance](#initinstance) функция-член для включения и загрузить список последних использованных файлов (MRU) и последнего предварительного просмотра состояния.

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Параметры

*nMaxMRU*<br/>
Количество недавно использовавшихся файлов для отслеживания.

### <a name="remarks"></a>Примечания

Если *nMaxMRU* равно 0, список последних выбиравшихся файлов не будет поддерживаться.

##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode

Значение TRUE, если приложение находится в режиме контекст справки (обычно вызывается с SHIFT + F1); в противном случае — значение FALSE.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Примечания

В режиме контекста справки курсор становится вопросительный знак и пользователь может перемещать экран сведений. Изучите этот флаг, если вы хотите реализовать специальной обработки в режиме справки. `m_bHelpMode` — это открытая переменная типа BOOL.

##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags

Флаги, которые определяют поведение диспетчера перезапуска.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Примечания

Чтобы включить диспетчер перезапуска, задайте `m_dwRestartManagerSupportFlags` поведение, которое требуется. В следующей таблице показаны доступные флаги.

|||
|-|-|
|Flag|Описание:|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Приложение регистрируется с помощью [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Диспетчер перезапуска несет ответственность за перезапуска приложения, если она неожиданно завершает работу.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Приложение регистрируется с диспетчером перезапуска и диспетчер перезапуска вызывает функцию обратного вызова восстановления, после его перезапуска приложения. Функция обратного вызова для восстановления по умолчанию является [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Включена функция автоматического сохранения и преждевременном прекращении работы диспетчера перезапуска открытые документы при повторном запуске приложения.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Включена функция автоматического сохранения и преждевременном прекращении работы диспетчера перезапуска открытые документы с регулярным интервалом. Временной интервал определяется параметром [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|
|-AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Диспетчер перезапуска открывается ранее открытые документы после перезапуска приложения из непредвиденный выход. [Класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) обрабатывает хранения список открытых документов и их восстановление.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Диспетчер перезапуска предлагает пользователю восстановить автоматическое сохранение файлов после перезапуска приложения. `CDataRecoveryHandler` Класс запрашивает пользователь.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|Объединение AFX_RESTART_MANAGER_SUPPORT_RESTART AFX_RESTART_MANAGER_SUPPORT_RECOVER и AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Union ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType

Тип этого элемента данных является перечисляемым типом AFX_HELP_TYPE, который определен в `CWinApp` класса.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Примечания

Перечисление AFX_HELP_TYPE определяется следующим образом:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Чтобы задать справки приложения на HTML-справки, вызовите [SetHelpMode](#sethelpmode) и укажите `afxHTMLHelp`.

- Чтобы задать помогут приложения WinHelp, вызовите `SetHelpMode` и укажите `afxWinHelp`.

##  <a name="m_hinstance"></a>  CWinApp::m_hInstance

Соответствует *hInstance* параметр передан по Windows для `WinMain`.

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Примечания

`m_hInstance` Данные-член — это дескриптор для текущего экземпляра приложения, работающие под Windows. Это значение возвращается с помощью глобальной функции [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance` — это открытая переменная типа HINSTANCE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine

Соответствует *lpCmdLine* параметр передан по Windows для `WinMain`.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Примечания

Указатель на заканчивающуюся нулем строку, указывающую командной строки для приложения. Используйте `m_lpCmdLine` для доступа к аргументы командной строки, введенные при запуске приложения пользователем. `m_lpCmdLine` — это открытая переменная типа LPTSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval

Продолжительность времени в миллисекундах между преждевременном прекращении работы.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Примечания

Диспетчер перезапуска в открытых документах автосохранения можно настроить через заданные интервалы времени. Если приложение не сохранять файлы, этот параметр не оказывает влияния.

##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow

Соответствует *nCmdShow* параметр передан по Windows для `WinMain`.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Примечания

Необходимо передать `m_nCmdShow` в качестве аргумента при вызове [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) для главного окна приложения. `m_nCmdShow` — это открытая переменная типа **int**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>  CWinApp::m_pActiveWnd

Этот элемент данных можно используйте для хранения указателя на главное окно приложения OLE-контейнера с вашей OLE сервера приложения активироваться на месте.

### <a name="remarks"></a>Примечания

Если этот элемент данных имеет значение NULL, приложение не локально активными.

Платформа присваивает переменную-член, когда фрейм окна активироваться приложением контейнера OLE на месте.

##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler

Указатель на обработчик восстановления данных для приложения.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Примечания

Обработчик восстановления данных приложения отслеживает открытые документы и преждевременном прекращении работы их. Инфраструктура использует обработчик восстановления данных для восстановления файлов автоматическое сохранение в том случае, когда приложение будет перезапущено после его неожиданно завершает работу. Дополнительные сведения см. в разделе [класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md).

##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName

Указывает имя приложения.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Примечания

Имя приложения могут поступать из параметров, переданных [CWinApp](#cwinapp) конструктор, или, если не указан, в строку ресурса с Идентификатором AFX_IDS_APP_TITLE. Если имя приложения не найден в ресурсе, он поступает из программы. Имя файла EXE.

Возвращаемый функцией глобального [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName` — это открытая переменная типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если присвоить значение `m_pszAppName`, он должен быть динамически выделен в куче. `CWinApp` Вызовы деструктора **бесплатный**() этого указателя. Многие будет использоваться `_tcsdup`()-функция библиотеки времени выполнения для выполнения распределения. Кроме того освободите память, связанную с текущим указателем перед назначением ему новое значение. Пример:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName

Содержит имя исполняемого файла приложения без расширения.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Примечания

В отличие от [m_pszAppName](#m_pszappname), это имя не может содержать пробелы. `m_pszExeName` — это открытая переменная типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если присвоить значение `m_pszExeName`, он должен быть динамически выделен в куче. `CWinApp` Вызовы деструктора **бесплатный**() этого указателя. Многие будет использоваться `_tcsdup`()-функция библиотеки времени выполнения для выполнения распределения. Кроме того освободите память, связанную с текущим указателем перед назначением ему новое значение. Пример:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath

Содержит путь к файлу справки приложения.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Примечания

По умолчанию инициализирует платформу `m_pszHelpFilePath` имя приложения с «. HLP» добавлен. Чтобы изменить имя файла справки, установите `m_pszHelpFilePath` указывал на строка, содержащая полное имя файла справки нужное. — Удобное место для этого в приложении [InitInstance](#initinstance) функции. `m_pszHelpFilePath` — это открытая переменная типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если присвоить значение `m_pszHelpFilePath`, он должен быть динамически выделен в куче. `CWinApp` Вызовы деструктора **бесплатный**() этого указателя. Многие будет использоваться `_tcsdup`()-функция библиотеки времени выполнения для выполнения распределения. Кроме того освободите память, связанную с текущим указателем перед назначением ему новое значение. Пример:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName

Содержит имя приложения. INI-файл.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Примечания

`m_pszProfileName` — это открытая переменная типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если присвоить значение `m_pszProfileName`, он должен быть динамически выделен в куче. `CWinApp` Вызовы деструктора **бесплатный**() этого указателя. Многие будет использоваться `_tcsdup`()-функция библиотеки времени выполнения для выполнения распределения. Кроме того освободите память, связанную с текущим указателем перед назначением ему новое значение. Пример:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey

Используется, чтобы определить место хранения, в реестре или INI-файл, параметры профиля приложения.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Примечания

Как правило этот элемент данных рассматривается как доступный только для чтения.

- Значение хранится в раздел реестра. Имя параметра профиля приложения добавляется следующий раздел реестра: HKEY_CURRENT_USER/Software/LocalAppWizard-Generated/.

Если присвоить значение `m_pszRegistryKey`, он должен быть динамически выделен в куче. `CWinApp` Вызовы деструктора **бесплатный**() этого указателя. Многие будет использоваться `_tcsdup`()-функция библиотеки времени выполнения для выполнения распределения. Кроме того освободите память, связанную с текущим указателем перед назначением ему новое значение. Пример:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID

Идентификатор модели пользователя приложения.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Примечания

##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp

Обрабатывает клавиши SHIFT + F1 справки в приложении.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` инструкцию, чтобы ваши `CWinApp` класса схему сообщений, а также добавить элемента таблицы сочетаний клавиш, обычно SHIFT + F1, чтобы включить эту функцию-член.

`OnContextHelp` переводит приложение в режим справки. Курсор изменения стрелки и вопросительного знака и пользователь может затем наведите указатель мыши и нажмите левую кнопку мыши для выбора диалоговое окно, окно, меню или кнопки. Эта функция-член извлекает контекст справки объекта под курсором и вызывает функцию Windows WinHelp с помощью этого контекста справки.

##  <a name="onddecommand"></a>  CWinApp::OnDDECommand

Вызывается платформой, когда окно главного фрейма получает DDE выполнения сообщения.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Параметры

*lpszCommand*<br/>
Указывает строку команды DDE, полученные приложением.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда обработана; в противном случае 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию проверяет, является ли команда запроса на открытие документа и если да, открывает указанный документ. Диспетчер файлов Windows обычно отправляет такие DDE командной строки, при двойном щелчке файла данных. Переопределите эту функцию для обработки других DDE выполнение команд, таких как команду для печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>  CWinApp::OnFileNew

Реализует id_file_new-команда.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_FILE_NEW, OnFileNew )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнение команды создания файла.

См. в разделе [технические 22 Примечание](../../mfc/tn022-standard-commands-implementation.md) сведения на поведение по умолчанию и рекомендации о том, как переопределить эту функцию-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>  CWinApp::OnFileOpen

Реализует id_file_open-команда.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнение команды открытия файла.

Сведения о поведении по умолчанию и рекомендации о том, как переопределить эту функцию-член, см. в разделе [технические 22 Примечание](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup

Реализует id_file_print_setup-команда.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнение команды печати файла.

Сведения о поведении по умолчанию и рекомендации о том, как переопределить эту функцию-член, см. в разделе [технические 22 Примечание](../../mfc/tn022-standard-commands-implementation.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>  CWinApp::OnHelp

Обрабатывает справку F1 в приложении (с использованием текущего контекста).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Примечания

Обычно вы также добавите запись сочетания клавиш для клавиши F1. Включение клавиши F1 — только соглашение, не является обязательным.

Необходимо добавить `ON_COMMAND( ID_HELP, OnHelp )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, вызывается платформой, когда пользователь нажимает клавишу F1.

Реализация по умолчанию эта функция обработчика сообщений определяет контекст справки, соответствующий текущее окно, диалоговое окно или пункт меню, а затем вызывает WINHELP. EXE-ФАЙЛА. Если контекст, в настоящее время недоступен, функция использует контекст по умолчанию.

Переопределите эта функция-член для задания контекста справки на что-нибудь кроме окна, диалоговое окно, пункт меню или кнопки панели инструментов, который в данный момент имеет фокус. Вызовите `WinHelp` с требуемым помочь идентификатор контекста.

##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder

Обрабатывает команды ID_HELP_FINDER и ID_DEFAULT_HELP.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, платформа вызывает эту функцию обработчика сообщений, при выборе пользователем приложения поиска справки команду, вызываемую `WinHelp` со стандартом **HELP_FINDER** раздела.

##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex

Id_help_index-команда обрабатывает и предоставляет раздел справки по умолчанию.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Если параметр включен, платформа вызывает эту функцию обработчика сообщений, при выборе пользователем приложения индекс справки команду, вызываемую `WinHelp` со стандартом **HELP_INDEX** раздела.

##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing

Обрабатывает id_help_using-команда.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Примечания

Необходимо добавить `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` инструкцию, чтобы ваши `CWinApp` схему класса сообщений, чтобы включить эту функцию-член. Платформа вызывает эту функцию обработчика сообщений, при выборе пользователем приложения справку, используя команду, вызываемую `WinHelp` приложения со стандартом **HELP_HELPONHELP** раздела.

##  <a name="onidle"></a>  CWinApp::OnIdle

Переопределите эта функция-член для выполнения обработки времени простоя.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Значение счетчика увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений приложения является пустым. Этот счетчик обнуляется каждый раз при обработке нового сообщения. Можно использовать *lCount* параметр, чтобы определить относительный продолжительность времени, приложение бездействует без обработки сообщения.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, чтобы получать более обработки время простоя; 0, если потребуется больше времени простоя.

### <a name="remarks"></a>Примечания

`OnIdle` функция вызывается в цикл обработки сообщений по умолчанию, когда очередь сообщений приложения является пустым. Используйте переопределение для вызова свой опыт простоя обработчика задач.

`OnIdle` должен возвращать 0, чтобы указать, что без периодов простоя обработки является обязательным. *LCount* параметр увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений пуста и сбрасывается в 0 каждый раз при обработке нового сообщения. Можно вызвать в разных простоя подпрограммы, исходя из этого числа.

Далее перечислены обработка пустых циклов.

1. Если цикл обработки сообщений в библиотеке Microsoft Foundation Class проверяет очереди сообщений и не находит ожидающих сообщений, он вызывает `OnIdle` для объекта приложения и предоставляет 0 как *lCount* аргумент.

2. `OnIdle` выполняет определенную обработку и возвращает ненулевое значение, указывающее, она должна быть вызвана снова сделать дальнейшей обработки.

3. Цикл обработки сообщений снова проверяет очереди сообщений. Если ожидающих сообщений нет, он вызывает `OnIdle` опять же, увеличивая *lCount* аргумент.

4. В итоге `OnIdle` обработав все его задачи периода бездействия и возвращает значение 0. Это означает, что цикл обработки сообщений, чтобы остановить вызов `OnIdle` до получения следующего сообщения из очереди сообщений, после чего цикла простоя перезапускается с аргументом, равным 0.

Не выполняйте упрощения продолжительных задач во время `OnIdle` так, как приложение не может обрабатывать ввод данных пользователем до `OnIdle` возвращает.

> [!NOTE]
> Реализация по умолчанию `OnIdle` обновлений командные объекты пользовательского интерфейса, например пункты меню и кнопки панели инструментов, и он выполняет очистку структуры внутренних данных. Таким образом Если переопределить `OnIdle`, необходимо вызвать `CWinApp::OnIdle` с `lCount` в переопределенные версии. Сначала вызвать обработка бездействия все базового класса (то есть до базового класса `OnIdle` возвращает значение 0). Если вам нужно выполнять работу до завершения обработки базового класса, просмотрите реализацию базового класса для выбора соответствующих *lCount* во время которого будет выполняться.

Если вы не хотите `OnIdle` вызываться всякий раз, когда сообщение извлекается из очереди сообщений, можно переопределить [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Если приложение установило очень короткий таймера, или если система отправляет сообщение WM_SYSTIMER, затем `OnIdle` будет вызываться несколько раз и привести к снижению производительности.

### <a name="example"></a>Пример

В следующих двух примерах показано как использовать `OnIdle`. В первом примере обработка две задачи периода бездействия с помощью *lCount* аргумент, чтобы приоритет задачи. Первая задача — высокий приоритет, и делать их по мере возможности. Вторая задача менее важно и должна выполняться только в том случае, если имеется длинная пауза в ввод данных пользователем. Обратите внимание на вызов к версии базового класса `OnIdle`. Во втором примере управляет группой задач периода бездействия системы с разными приоритетами.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>  CWinApp::OpenDocumentFile

Платформа вызывает этот метод, чтобы открыть именованный [CDocument](../../mfc/reference/cdocument-class.md) файл для приложения.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
[in] Имя файла для открытия.

*bAddToMRU*<br/>
[in] Значение TRUE указывает, что документ является одним из последних файлов; Значение FALSE указывает, что документ не является ни один из последних файлов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CDocument` Если успешно; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Если документ с таким именем уже открыт, первое окно фрейма, содержащего этот документ получит фокус. Если приложение поддерживает несколько шаблонов документов, платформа использует расширение имени файла для поиска соответствующего шаблона документа для загрузки документа. В случае успешного выполнения документ затем шаблон создает фрейм окна и представление для документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine

Вызов этой функции-члена для командной строки и отправку параметров, поочередно, [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*rCmdInfo*<br/>
Ссылку на [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) объекта.

### <a name="remarks"></a>Примечания

При запуске нового проекта MFC с помощью мастера приложений, мастер приложений создаст локальный экземпляр `CCommandLineInfo`, а затем вызвать `ProcessShellCommand` и `ParseCommandLine` в [InitInstance](#initinstance) функция-член. В командной строке выполняется по маршруту, описанных ниже:

1. После создания в `InitInstance`, `CCommandLineInfo` объект передается `ParseCommandLine`.

2. `ParseCommandLine` затем вызывает `CCommandLineInfo::ParseParam` несколько раз, один раз для каждого параметра.

3. `ParseParam` заполняет `CCommandLineInfo` объект, который затем передается [ProcessShellCommand](#processshellcommand).

4. `ProcessShellCommand` обрабатывает аргументы командной строки и флаги.

Обратите внимание, что вы можете вызвать `ParseCommandLine` напрямую, при необходимости.

Описание флагов командной строки, см. в разделе [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

##  <a name="pretranslatemessage"></a>  CWinApp::PreTranslateMessage

Переопределите эту функцию для фильтрации сообщений окон до их передачи функциям Windows [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) реализация по умолчанию выполняет сочетания клавиш перевод, поэтому необходимо вызвать `CWinApp::PreTranslateMessage` функция-член в переопределенные версии.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) структуру, содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение был полностью обработан в `PreTranslateMessage` и не должны обрабатываться Дополнительно. Нуль, если сообщения должны обрабатываться обычным образом.

##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter

Функция-ловушка framework вызывает эта функция-член для фильтрации и реагировать на них некоторых сообщений Windows.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*код*<br/>
Указывает код обработчика. Эта функция-член использует код для определения способа обработки *lpMsg.*

*lpMsg*<br/>
Указатель на Windows [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) структуры.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если сообщение обработано; в противном случае 0.

### <a name="remarks"></a>Примечания

Функция-ловушка обрабатывает события перед их отправкой в обычное сообщение приложения обработки.

Если переопределить это дополнительная возможность, необходимо вызвать версии базового класса для обеспечения платформы подключить обработки.

##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand

Эта функция-член вызывается [InitInstance](#initinstance) принимать параметры, передаваемые из `CCommandLineInfo` объекта, идентифицируемое по *rCmdInfo*и выполнить указанное действие.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*rCmdInfo*<br/>
Ссылку на [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) объекта.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если команда оболочки успешно обработан. Если 0, возвращается значение FALSE из [InitInstance](#initinstance).

### <a name="remarks"></a>Примечания

При запуске нового проекта MFC с помощью мастера приложений, мастер приложений создаст локальный экземпляр `CCommandLineInfo`, а затем вызвать `ProcessShellCommand` и [ParseCommandLine](#parsecommandline) в `InitInstance` функция-член. В командной строке выполняется по маршруту, описанных ниже:

1. После создания в `InitInstance`, `CCommandLineInfo` объект передается `ParseCommandLine`.

2. `ParseCommandLine` затем вызывает [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) несколько раз, один раз для каждого параметра.

3. `ParseParam` заполняет `CCommandLineInfo` объект, который затем передается `ProcessShellCommand`.

4. `ProcessShellCommand` обрабатывает аргументы командной строки и флаги.

Члены данных `CCommandLineInfo` объекта, идентифицируемого по [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), имеют следующий тип перечисления, который определен в `CCommandLineInfo` класса.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Краткое описание каждого из этих значений, см. в разделе `CCommandLineInfo::m_nShellCommand`.

##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException

Эта функция-член вызывается платформой, каждый раз, когда обработчик не перехватывает исключение, создаваемое в одном из сообщения приложения или обработчиков команд.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*e*<br/>
Указатель на неперехваченное исключение.

*pMsg*<br/>
Объект [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg) структуру, содержащую сведения о сообщения windows, которое вызвало платформа для создания исключения.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое должны быть возвращены для Windows. Обычно это 0L для сообщения windows, 1L (TRUE) для командных сообщений.

### <a name="remarks"></a>Примечания

Не вызывайте напрямую этой функцией-членом.

Реализация по умолчанию эта функция-член создает окно сообщения. Если неперехваченное исключение происходит с меню, панели инструментов или сбоя команды сочетаний клавиш, в окне сообщения отображается сообщение «Не удалось выполнить команду»; в противном случае он отображает сообщение «Внутренняя ошибка приложения».

Переопределите эта функция-член для предоставления глобальной обработки исключений. Вызовите базовые функциональные возможности только в том случае, если вы хотите отобразить в окне сообщения.

##  <a name="register"></a>  CWinApp::Register

Выполняет все задачи регистрации, не обрабатываются `RegisterShellFileTypes`.

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию просто возвращает значение TRUE. Переопределите эту функцию, чтобы предоставить любые инструкции по регистрации настраиваемого.

##  <a name="registershellfiletypes"></a>  CWinApp::RegisterShellFileTypes

Вызов этой функции-члена для регистрации всех типов документов приложения с помощью диспетчера файлов Windows.

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Параметры

*bCompat*<br/>
[in] Значение TRUE добавляет регистрационных записей для команды оболочки, печати и печатать на, что позволяет пользователю печатать файлы непосредственно из оболочки или перетащив его в объект printer. Он также добавляет ключ DefaultIcon. По умолчанию этот параметр имеет значение FALSE для обеспечения обратной совместимости.

### <a name="remarks"></a>Примечания

Это позволяет пользователю открыть файл данных, создаваемых приложением, дважды щелкнув его из диспетчера файлов. Вызовите `RegisterShellFileTypes` после вызова метода [AddDocTemplate](#adddoctemplate) для каждого из шаблонов документов в приложении. Также вызвать [EnableShellOpen](#enableshellopen) при вызове функции-члена `RegisterShellFileTypes`.

`RegisterShellFileTypes` выполняет итерацию по списку [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объектов, что приложение поддерживает и, для каждого шаблона документа, добавляет записи в базу данных регистрации, Windows поддерживает для сопоставления файлов. Диспетчер файлов эти записи используются для открытия файла данных, когда пользователь дважды щелкает его. Это устраняет необходимость для отправки. REG-файл вместе с приложением.

> [!NOTE]
> `RegisterShellFileTypes` работает, только если пользователь запускает программу с правами администратора. Если программа не имеет прав администратора, его невозможно изменить разделы реестра.

Если база данных регистрации уже связан с расширением имени файла данного с другим типом файла, создается без новой связи. См. в разделе `CDocTemplate` класс для формата строки, необходимые для регистрации этой информации.

##  <a name="registerwithrestartmanager"></a>  CWinApp::RegisterWithRestartManager

Регистрирует приложение с диспетчером перезапуска.

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>Параметры

|||
|-|-|
|Параметр|Описание:|
|*bRegisterRecoveryCallback*|[in] Значение TRUE указывает, что этот экземпляр приложения использует функцию обратного вызова восстановления; Значение FALSE указывает, что это не так. Платформа вызывает функцию обратного вызова восстановления, когда приложение неожиданно завершает работу. Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartIdentifier*|[in] Уникальная строка, определяющая данного экземпляра диспетчера перезапуска. Идентификатор диспетчера перезапуска является уникальным для каждого экземпляра приложения.|
|*pwzCommandLineArgs*|[in] Строка, содержащая все лишние аргументы из командной строки.|
|*dwRestartFlags*|[in] Необязательные флаги диспетчера перезапуска. Дополнительные сведения см. в разделе "Примечания".|
|*pRecoveryCallback*|[in] Функция обратного вызова для восстановления. Эта функция должна принимать параметр LPVOID как входные данные и возвращать значение типа DWORD. Функция обратного вызова для восстановления по умолчанию является `CWinApp::ApplicationRecoveryCallback`.|
|*lpvParam*|[in] Входной параметр для восстановления функции обратного вызова. Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|[in] Продолжительность времени ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата. Этот параметр указывается в миллисекундах.|
|*dwCallbackFlags*|[in] Флаги, переданные в функцию обратного вызова восстановления. Зарезервировано для будущего использования.|

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если метод выполнен успешно; в противном случае — код ошибки.

### <a name="remarks"></a>Примечания

Если в приложении используется реализация MFC по умолчанию автоматическое сохранение файлов, следует использовать простую версию `RegisterWithRestartManager`. Используйте сложные версию `RegisterWithRestartManager` Если вы хотите настроить автосохранения поведение приложения.

При вызове этого метода с пустой строкой для *strRestartIdentifier*, `RegisterWithRestartManager` создает диспетчер строкой уникального идентификатора для перезапуска данного экземпляра.

Если приложение неожиданно завершает работу, диспетчер перезапуска перезапускает приложение из командной строки и предоставляет уникальный перезапустите идентификатор, что необязательный аргумент. В этом случае платформа вызывает `RegisterWithRestartManager` два раза. Первый вызов поступает из [CWinApp::InitInstance](#initinstance) с пустой строкой для идентификатора строки. Затем метод [CWinApp::ProcessShellCommand](#processshellcommand) вызовы `RegisterWithRestartManager` с идентификатором уникальный перезапуска.

После регистрации приложения с диспетчером перезапуска, диспетчер перезапуска отслеживает приложение. Если приложение неожиданно завершает работу, диспетчер перезапуска вызывает функцию обратного вызова восстановления во время завершение работы процесса. Ожиданий диспетчера перезапуска *dwPingInterval* ответа из функции обратного вызова восстановления. Если функция обратного вызова восстановления не отвечает в течение этого времени, приложение завершает работу без выполнения функции обратного вызова восстановления.

По умолчанию dwRestartFlags не поддерживаются, но предоставляются для использования в будущем. Возможные значения *dwRestartFlags* таковы:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart

Определяет, открывается ли диспетчер перезапуска повторно файлы, которые были открыты, когда приложение неожиданно.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска снова открывает ранее открытые файлы; Значение FALSE указывает, что диспетчер перезапуска — нет.

##  <a name="restartinstance"></a>  CWinApp::RestartInstance

Обрабатывает инициированным диспетчером перезапуска перезапуска приложения.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если обработчик восстановления данных открывает ранее открытые документы; Значение FALSE, если обработчик восстановления данных возникла ошибка, или если нет ранее открытые документы.

### <a name="remarks"></a>Примечания

Когда диспетчер перезапуска перезапускает приложение, этот метод вызывается платформой. Этот метод извлекает обработчик восстановления данных и восстанавливает файлы, автоматическое сохранение. Этот метод вызывает метод [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) для определения, требуется ли пользователю для восстановления файлов автоматическое сохранение.

Этот метод возвращает значение FALSE, если [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) определяет факт нет открытых документов. Если нет открытых документов, обычно запуска приложения.

##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart

Определяет, восстанавливает ли диспетчер перезапуска автоматическое сохранение файлов после его перезапуска приложения.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска восстанавливает файлы, автоматическое сохранение; Значение FALSE указывает, что диспетчер перезапуска — нет.

##  <a name="run"></a>  CWinApp::Run

Предоставляет цикл обработки сообщений по умолчанию.

```
virtual int Run();
```

### <a name="return-value"></a>Возвращаемое значение

**Int** значение, которое возвращается методом `WinMain`.

### <a name="remarks"></a>Примечания

`Run` Получает и отправляет сообщения, Windows, пока приложение не получит сообщение WM_QUIT. Если очередь сообщений приложения в настоящее время не содержит сообщений, `Run` вызовы [OnIdle](#onidle) для выполнения обработки времени простоя. Входящие сообщения перейти к [PreTranslateMessage](#pretranslatemessage) функция-член для специальной обработки, а затем в функцию Windows `TranslateMessage` для перевода на стандартной клавиатуре; Наконец, `DispatchMessage` вызове функции Windows.

`Run` редко переопределяется, но его можно переопределить для предоставления особое поведение.

##  <a name="runautomated"></a>  CWinApp::RunAutomated

Вызывайте эту функцию, чтобы определить ли " **/Automation**«или» **-автоматизации**" параметр присутствует, которое указывает, была ли запущена клиентским приложением серверное приложение.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если параметр был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Если он присутствует, параметр удаляется из командной строки. Дополнительные сведения о OLE-автоматизации см. в статье [серверы автоматизации](../../mfc/automation-servers.md).

##  <a name="runembedded"></a>  CWinApp::RunEmbedded

Вызывайте эту функцию, чтобы определить ли " **/Embedding**«или» **-внедрения**" параметр присутствует, которое указывает, была ли запущена клиентским приложением серверное приложение.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если параметр был найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Если он присутствует, параметр удаляется из командной строки. Дополнительные сведения о внедрении см. в статье [серверов: Реализация сервера](../../mfc/servers-implementing-a-server.md).

##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified

Вызывается платформой для сохранения всех документов, когда окна главного фрейма приложения будет закрыта, или через сообщение WM_QUERYENDSESSION.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если безопасный для завершения работы приложения; 0, если это не безопасно завершить работу приложения.

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция-член вызывает [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) функция-член в свою очередь для всех измененных документов в приложении.

##  <a name="selectprinter"></a>  CWinApp::SelectPrinter

Вызовите эту функцию-член для выбора конкретного принтера и отпустите принтера, который ранее был выбран в диалоговом окне печати.

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Параметры

*hDevNames*<br/>
Дескриптор [DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames) структура, определяющая драйвера, устройства, а также имена портов выходные данные конкретного принтера.

*hDevMode*<br/>
Дескриптор [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea) структуру, которая указывает сведения об инициализации устройства и среде принтера.

*bFreeOld*<br/>
Освобождает ранее выбранный принтер.

### <a name="remarks"></a>Примечания

Если оба *hDevMode* и *hDevNames* имеют значение NULL, `SelectPrinter` использует текущего принтера по умолчанию.

##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode

Задает тип справки приложения.

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Параметры

*eHelpType*<br/>
Указывает тип справки для использования. См. в разделе [CWinApp::m_eHelpType](#m_ehelptype) Дополнительные сведения.

### <a name="remarks"></a>Примечания

Задает тип справки приложения.

Чтобы задать тип справки приложения HTMLHelp, можно вызвать [EnableHTMLHelp](#enablehtmlhelp). При вызове метода `EnableHTMLHelp`, ваше приложение должно использовать HTMLHelp как его приложение справки. Если вы хотите изменить для использования WinHelp, можно вызвать `SetHelpMode` и задайте *eHelpType* для `afxWinHelp`.

##  <a name="setregistrykey"></a>  CWinApp::SetRegistryKey

В результате параметры приложения, чтобы хранить в реестре, вместо INI-файлы.

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Параметры

*lpszRegistryKey*<br/>
Указатель на строку, содержащую имя ключа.

*nIDRegistryKey*<br/>
Идентификатор строкового ресурса, содержащего имя раздела реестра.

### <a name="remarks"></a>Примечания

Эта функция задает *m_pszRegistryKey*, который затем используется `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, и `WriteProfileString` функциями-членами `CWinApp`. Если эта функция был вызван, список последних использованных файлов (MRU) также хранится в реестре. Раздел реестра обычно является имя компании. Он хранится в ключе следующего вида: Раздел HKEY_CURRENT_USER\Software\\< название_организации\>\\< имя_приложения\>\\< имя раздела\>\\< имя значения\>.

##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery

Определяет, восстановилось ли диспетчер перезапуска приложения, которое неожиданно завершил работу.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что диспетчер перезапуска восстанавливает приложения; Значение FALSE указывает, что диспетчер перезапуска — нет.

##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval

Определяет, ли преждевременном прекращении работы диспетчера перезапуска открывать документы с регулярным интервалом.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что преждевременном прекращении работы диспетчера перезапуска открывать документы; Значение FALSE указывает, что диспетчер перезапуска — нет.

##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart

Определяет, является ли преждевременном прекращении работы диспетчера перезапуска открытые документы при повторном запуске приложения.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что преждевременном прекращении работы диспетчера перезапуска открывать документы, при повторном запуске приложения; Значение FALSE указывает, что диспетчер перезапуска — нет.

##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager

Определяет, поддерживает ли приложение диспетчера перезапуска.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE указывает, что приложение поддерживает диспетчер перезапуска; Значение FALSE указывает, что приложение не поддерживает.

##  <a name="unregister"></a>  CWinApp::Unregister

Отменяет регистрацию всех файлов, зарегистрированных объектов приложения.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Примечания

`Unregister` Функция отменяет процесс регистрации, выполняемый в объекте приложения и [зарегистрировать](#register) функции. Как правило обе функции вызываются неявно с MFC и поэтому он не будет отображаться в коде.

Переопределите эту функцию для отмены регистрации пользовательского действия.

##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes

Вызовите эту функцию-член для отмены регистрации всех типов документов приложения с помощью диспетчера файлов Windows.

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>  CWinApp::WinHelp

Вызов этой функции-члена для вызова приложения WinHelp.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Параметры

*dwData*<br/>
Указывает дополнительные данные. Значение, используемое зависит от значения *nCmd* параметра.

*nCmd*<br/>
Задает тип запрошенной справки. Список возможных значений и как они влияют на *dwData* параметр, см. в разделе [WinHelp](/windows/desktop/api/winuser/nf-winuser-winhelpa) функции Windows.

### <a name="remarks"></a>Примечания

Кроме того, платформа вызывает эту функцию для вызова приложения WinHelp.

Платформа автоматически закроет приложения WinHelp, когда приложение завершает работу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>  CWinApp::WriteProfileBinary

Вызов этой функции-члена для записи двоичных данных в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий запись, в которую, значение которого записывается. Если запись не существует в указанном разделе, он создается.

*pData*<br/>
Указывает на данные для записи.

*nBytes*<br/>
Содержит число байтов для записи.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

В этом примере используется `CWinApp* pApp = AfxGetApp();` получить класс CWinApp, демонстрирующие способ, `WriteProfileBinary` и `GetProfileBinary` можно использовать из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Другой пример, см. в примере [CWinApp::GetProfileBinary](#getprofilebinary).

##  <a name="writeprofileint"></a>  CWinApp::WriteProfileInt

Вызов этой функции-члена для записи заданного значения в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий запись, в которую, значение которого записывается. Если запись не существует в указанном разделе, он создается.

*nValue*<br/>
Содержит значение для записи.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

В этом примере используется `CWinApp* pApp = AfxGetApp();` получить класс CWinApp, демонстрирующие способ, `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, и `GetProfileInt` можно использовать из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример, см. в примере [CWinApp::GetProfileInt](#getprofileint).

##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString

Вызывайте эту функцию члена для записи указанную строку в указанный раздел реестра приложения или. INI-файл.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указатель на заканчивающуюся нулем строку, указывающее раздел, содержащий запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.

*lpszEntry*<br/>
Указатель на заканчивающуюся нулем строку, содержащий запись, в которую, значение которого записывается. Если запись не существует в указанном разделе, он создается. Если этот параметр имеет значение NULL, определяемое разделе *lpszSection* удаляется.

*lpszValue*<br/>
Указывает на строку для записи. Если этот параметр имеет значение NULL, операция, заданный *lpszEntry* удаляется параметр.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Другой пример, см. в примере [CWinApp::GetProfileInt](#getprofileint).

##  <a name="setappid"></a>  CWinApp::SetAppID

Явно задает идентификатор модели пользователя приложения для приложения. Этот метод должен вызываться до никакого пользовательского интерфейса предоставляется пользователю (лучше всего — это конструктор приложения).

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Параметры

*lpcszAppID*<br/>
Указывает идентификатор модели пользователя приложения.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[Класс CWinThread](../../mfc/reference/cwinthread-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)
