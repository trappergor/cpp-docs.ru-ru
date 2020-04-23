---
title: Класс CWinApp
ms.date: 07/15/2019
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
ms.openlocfilehash: 4bb1ade4182424cbdcbf0d7ba69af88bbb88abe6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750669"
---
# <a name="cwinapp-class"></a>Класс CWinApp

Базовый класс, от которого необходимо наследовать объект приложения Windows.

## <a name="syntax"></a>Синтаксис

```
class CWinApp : public CWinThread
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinApp::CWinApp](#cwinapp)|Формирует объект `CWinApp`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp::AddDocTemplate](#adddoctemplate)|Добавляет шаблон документа в список доступных шаблонов документов приложения.|
|[CWinApp:Addtorecentfilelist](#addtorecentfilelist)|Добавляет имя файла в список самых недавно используемых файлов (MRU).|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Вызывается по фреймворку при неожиданном выходе приложения.|
|[CWinApp::CloseAllDocuments](#closealldocuments)|Закрывает все открытые документы.|
|[CWinApp::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера.|
|[CWinApp::DelRegTree](#delregtree)|Удаляет указанный ключ и все его подки.|
|[CWinApp::DoMessageBox](#domessagebox)|Реализует [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для приложения.|
|[CWinApp::DoWaitCursor](#dowaitcursor)|Включает курсор ожидания.|
|[CWinApp:EnableD2DSupport](#enabled2dsupport)|Позволяет прикладной поддержки D2D. Данный метод следует вызывать до инициализации основного окна.|
|[CWinApp:EnableHtmlHelp](#enablehtmlhelp)|Реализует HTMLHelp для приложения, а не WinHelp.|
|[CWinApp::EnableTaskbarВзаимодействие](#enabletaskbarinteraction)|Обеспечивает взаимодействие панели задач.|
|[CWinApp::ExitInstance](#exitinstance)|Переопределение для очистки при завершении приложения.|
|[CWinApp::GetApplicationВосстановлениеПараметр](#getapplicationrecoveryparameter)|Извлекает параметр ввода для метода восстановления приложения.|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Возвращает время, в течение которого менеджер перезагрузки ждет возврата функции возврата.|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Возвращает флаги для менеджера перезагрузки.|
|[CWinApp:GetAppRegistryKey](#getappregistrykey)|Возвращает ключ\\для HKEY_CURRENT_USER "Программное обеспечение",RegistryKey-ProfileName.|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Получает обработчик восстановления данных для данного экземпляра приложения.|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Извлекает положение первого шаблона документа.|
|[CWinApp:GetHelpMode](#gethelpmode)|Извлекает тип справки, используемой приложением.|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Извлекает положение шаблона документа. Может быть использован рекурсивно.|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Извлекает по умолчанию устройство принтера.|
|[CWinApp:GetProfileBinary](#getprofilebinary)|Извлекает двоичные данные из записи в приложении. Файл INI.|
|[CWinApp:GetProfileInt](#getprofileint)|Извлекает несколько с того, что запись в приложении. Файл INI.|
|[CWinApp:GetProfileString](#getprofilestring)|Извлекает строку из записи в приложении. Файл INI.|
|[CWinApp::GetSectionKey](#getsectionkey)|Возвращает ключ\\для HKEY_CURRENT_USER "Программное обеспечение", - "РегистраторКей"ПриложениеName-lpszSection.|
|[CWinApp::HideApplication](#hideapplication)|Скрывает заявку перед закрытием всех документов.|
|[CWinApp::HtmlHelp](#htmlhelp)|Вызывает `HTMLHelp` функцию Windows.|
|[CWinApp::InitInstance](#initinstance)|Переопределение для выполнения инициализации экземпляра Windows, например, создание оконных объектов.|
|[CWinApp::IsTaskbarВзаимодействие](#istaskbarinteractionenabled)|Сообщает, включено ли взаимодействие панели задач Windows 7.|
|[CWinApp::LoadCursor](#loadcursor)|Загружает ресурс курсора.|
|[CWinApp::LoadIcon](#loadicon)|Загружает ресурс значка.|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Загружает предопределенный курсор OEM Windows, который **OCR_** константы, указанные в WINDOWS. H.|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Загружает предопределенный значок Windows OEM, который **OIC_** константы, указанные в WINDOWS. H.|
|[CWinApp:LoadStandardCursor](#loadstandardcursor)|Загружает предопределенный курсор Windows, который **IDC_** константы, указанные в WINDOWS. H.|
|[CWinApp:LoadStandardIcon](#loadstandardicon)|Загружает значок Windows, который **IDI_** констант, указанный в WINDOWS. H.|
|[CWinApp::OnDDECommand](#onddecommand)|Вызывается рамками в ответ на динамический обмен данными (DDE) выполнить команду.|
|[CWinApp::Onidle](#onidle)|Переопределение для выполнения обработки простоя приложения.|
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Вызывается в рамках, чтобы открыть документ из файла.|
|[CWinApp::ParseCommandLine](#parsecommandline)|Параметры отдельных параметров и флагов в командной строке.|
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Фильтры сообщений, прежде чем они будут отправлены на функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage.](/windows/win32/api/winuser/nf-winuser-dispatchmessage)|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенные сообщения, прежде чем они достигнут приложения.|
|[CWinApp::ProcessShellCommand](#processshellcommand)|Обработка аргументов и флагов командной строки.|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, брошенные обработчиками сообщений и команд.|
|[CWinApp::Регистрация](#register)|Выполняет индивидуальную регистрацию.|
|[CWinApp:RegisterWithRestartManager](#registerwithrestartmanager)|Регистрирует приложение с менеджером перезагрузки.|
|[CWinApp::ReopenPreviousFilesatRestart](#reopenpreviousfilesatrestart)|Определяет, возобновляет ли менеджер перезагрузки файлы, которые были открыты при неожиданном выходе приложения.|
|[CWinApp::RestartInstance](#restartinstance)|Обрабатывает перезагрузку приложения, инициированную менеджером перезагрузки.|
|[CWinApp::RestoreAutosavedFilesatRestart](#restoreautosavedfilesatrestart)|Определяет, восстанавливает ли менеджер перезагрузки автоматически сохраненные файлы при перезагрузке приложения.|
|[CWinApp::Run](#run)|Запускает цикл сообщения по умолчанию. Переопределение для настройки цикла сообщений.|
|[CWinApp::RunAutomated](#runautomated)|Тестирует командную строку приложения для опции **/Automation.** Устаревшее. Вместо этого используйте значение в [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) после вызова [ParseCommandLine](#parsecommandline).|
|[CWinApp::RunEmbedded](#runembedded)|Тестирует командную строку приложения для опции **/Embedding.** Устаревшее. Вместо этого используйте значение в [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) после вызова [ParseCommandLine](#parsecommandline).|
|[CWinApp:SaveAllModified](#saveallmodified)|Побуждает пользователя сохранить все измененные документы.|
|[CWinApp::SelectPrinter](#selectprinter)|Выбирает принтер, ранее указанный пользователем, через поле диалога печати.|
|[CWinApp:SetHelpMode](#sethelpmode)|Устанавливает и инициализирует тип справки, используемой приложением.|
|[CWinApp::ПоддержкаВосстановления приложений](#supportsapplicationrecovery)|Определяет, восстанавливает ли менеджер перезагрузки приложение, которое неожиданно вышло.|
|[CWinApp::SupportsAutosaveatInterval](#supportsautosaveatinterval)|Определяет, автоматически ли менеджер перезагрузки сохраняет открытые документы с регулярным интервалом.|
|[CWinApp::SupportsAutosaveatRestart](#supportsautosaveatrestart)|Определяет, автоматически ли менеджер перезагрузки сохраняет открытые документы при перезагрузке приложения.|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Определяет, поддерживает ли приложение менеджер перезагрузки.|
|[CWinApp::Unregister](#unregister)|Не регистрирует все, что, `CWinApp` как известно, зарегистрировано объектом.|
|[CWinApp::WinHelp](#winhelp)|Вызывает `WinHelp` функцию Windows.|
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Записывает двоичные данные на запись в приложении . Файл INI.|
|[CWinApp::WriteProfileInt](#writeprofileint)|Записывает несколько к записи в приложении . Файл INI.|
|[CWinApp::WriteProfileString](#writeprofilestring)|Записывает строку к записи в приложении . Файл INI.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CWinApp:EnableShellOpen](#enableshellopen)|Позволяет пользователю открывать файлы данных из windows File Manager.|
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Стандарт загрузки . InI настройки файлов и позволяет функцию списка файлов MRU.|
|[CWinApp::OnContextHelp](#oncontexthelp)|Ручки справки SHIFT-F1 в приложении.|
|[CWinApp::OnFileNew](#onfilenew)|Реализует команду ID_FILE_NEW.|
|[CWinApp::OnFileOpen](#onfileopen)|Реализует команду ID_FILE_OPEN.|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Реализует команду ID_FILE_PRINT_SETUP.|
|[CWinApp::OnHelp](#onhelp)|Обрабатывает справку F1 в приложении (с использованием текущего контекста).|
|[CWinApp::OnHelpFinder](#onhelpfinder)|Обрабатывает ID_HELP_FINDER и ID_DEFAULT_HELP команды.|
|[CWinApp::Хелпиндекс](#onhelpindex)|Обрабатывает ID_HELP_INDEX команду и предоставляет тему справки по умолчанию.|
|[CWinApp::OnHelpUsing](#onhelpusing)|Обрабатывает команду ID_HELP_USING.|
|[CWinApp:RegisterShellFileTypes](#registershellfiletypes)|Регистрирует все типы документов приложения с помощью менеджера файлов Windows.|
|[CWinApp::SetAppID](#setappid)|Явно устанавливает идентификатор модели пользователя приложения для приложения. Этот метод следует назвать до того, как пользовательский интерфейс будет представлен пользователю (лучшее место - конструктор приложения).|
|[CWinApp::SetRegistryKey](#setregistrykey)|Вызывает настройки приложения, которые будут храниться в реестре вместо . Файлы INI.|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Отменить регистрацию всех типов документов приложения с помощью диспетчера файлов Windows.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Указывает, находится ли пользователь в контекстном режиме справки (обычно на него ссылаются с SHIFT-F1).|
|[CWinApp::m_eHelpType](#m_ehelptype)|Определяет тип справки, используемой приложением.|
|[CWinApp::m_hInstance](#m_hinstance)|Определяет текущую экземпляр приложения.|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Указывает на нулевую строку, определяющую командную строку для приложения.|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Определяет, как окно должно быть показано на начальном этапе.|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Указатель на основное окно контейнерного приложения, когда сервер OLE находится на месте.|
|[CWinApp::m_pszAppID](#m_pszappid)|Идентификатор модели пользователя приложения.|
|[CWinApp::m_pszAppName](#m_pszappname)|Указывает имя приложения.|
|[CWinApp::m_pszExeName](#m_pszexename)|Название модуля приложения.|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Путь к файлу справки приложения.|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Приложение . Имя файла INI.|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Используется для определения полного ключа реестра для хранения параметров профиля приложения.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Флаги, определяющие, как ведет себя менеджер перезагрузки.|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Продолжительность времени в миллисекундах между автосавами.|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Указатель на обработчик восстановления данных для приложения.|

## <a name="remarks"></a>Remarks

Объект приложения предоставляет функции участника для инициализации приложения (и каждого экземпляра) и для запуска приложения.

Каждое приложение, используюееееееклассство `CWinApp`Фонда Майкрософт, может содержать только один объект, полученный из. Этот объект построен, когда построены другие глобальные объекты СЗ, и уже доступен, когда Windows вызывает `WinMain` функцию, которая поставляется библиотекой microsoft Foundation Class Library. Объявить ваш `CWinApp` производный объект на глобальном уровне.

При извлечении класса `CWinApp`приложений из функции участника InitInstance переопределить функцию [initInstance](#initinstance) для создания основного объекта окна приложения.

В дополнение `CWinApp` к функциям-членам Библиотека класса Фонда Майкрософт `CWinApp` предоставляет следующие глобальные функции для доступа к объекту и другой глобальной информации:

- [AfxGetApp](application-information-and-management.md#afxgetapp) Получает указатель на `CWinApp` объект.

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Получает ручку к текущему экземпляру приложения.

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Получает ручку ресурсов приложения.

- [AfxGetAppName](application-information-and-management.md#afxgetappname) Получает указатель на строку, содержащую имя приложения. Кроме того, если у вас `CWinApp` есть указатель на объект, используйте, `m_pszExeName` чтобы получить имя приложения.

См [CWinApp: Класс приложений](../../mfc/cwinapp-the-application-class.md) для получения дополнительной информации о `CWinApp` классе, включая обзор следующих вопросов:

- `CWinApp`-производный код, написанный Мастером Приложения.

- `CWinApp`роль в последовательности исполнения приложения.

- `CWinApp`'по умолчанию выполнения функций участника.

- `CWinApp`Ключевые переизлики.

Член `m_hPrevInstance` данных больше не существует. Чтобы определить, работает ли другой экземпляр приложения, используйте именованный mutex. Если открытие mutex не удается, то нет других экземпляров приложения работает.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cwinappadddoctemplate"></a><a name="adddoctemplate"></a>CWinApp::AddDocTemplate

Вызовите эту функцию участника, чтобы добавить шаблон документа в список доступных шаблонов документов, которые поддерживает приложение.

```cpp
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>Параметры

*pTemplate*<br/>
Указатель на `CDocTemplate` добавление.

### <a name="remarks"></a>Remarks

Вы должны добавить все шаблоны документов в приложение, прежде чем звонить [RegisterShellFileTypes](#registershellfiletypes).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

## <a name="cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>CWinApp:Addtorecentfilelist

Вызовите эту функцию участника, чтобы добавить *lpszPathName* в список файлов MRU.

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>Параметры

*lpszPathName*<br/>
Путь к файлу.

### <a name="remarks"></a>Remarks

Перед использованием этой функции участника loadStdProfileSettings следует вызвать функцию члена [LoadStdProfileSettings](#loadstdprofilesettings) для загрузки текущего списка файлов MRU.

Платформа вызывает эту функцию пользователя, когда он открывает файл или выполняет команду Save As для сохранения файла с новым именем.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

## <a name="cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback

Вызывается по фреймворку при неожиданном выходе приложения.

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>Параметры

*lpvParam*<br/>
[in] Зарезервирован для будущего использования.

### <a name="return-value"></a>Возвращаемое значение

0, если этот метод является успешным; ненулевой, если ошибка происходит.

### <a name="remarks"></a>Remarks

Если приложение поддерживает менеджер перезагрузки, фреймворк вызывает эту функцию при неожиданном выходе приложения.

Реализация по `ApplicationRecoveryCallback` умолчанию `CDataRecoveryHandler` использует для сохранения списка открытых в настоящее время документов в реестр. Этот метод не автоматически сохраняет файлы.

Чтобы настроить поведение, переопределить эту функцию в производном [классе CWinApp](../../mfc/reference/cwinapp-class.md) или передать свой собственный метод восстановления приложения в качестве параметра [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).

## <a name="cwinappclosealldocuments"></a><a name="closealldocuments"></a>CWinApp::CloseAllDocuments

Позвоните этой функции участника, чтобы закрыть все открытые документы перед выходом.

```cpp
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>Параметры

*bEndSession*<br/>
Уточняется, завершена ли сессия Windows. Это правда, если сессия в настоящее время завершена; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Позвоните в `CloseAllDocuments` [HideApplication](#hideapplication) перед вызовом.

## <a name="cwinappcreateprinterdc"></a><a name="createprinterdc"></a>CWinApp::CreatePrinterDC

Вызовите эту функцию участника для создания контекста устройства принтера (DC) из выбранного принтера.

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
Ссылка на контекст устройства принтера.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если контекст устройства принтера создан успешно; в противном случае 0.

### <a name="remarks"></a>Remarks

`CreatePrinterDC`инициализирует контекст устройства, который вы передаете в ссылку, так что вы можете использовать его для печати.

Если функция успешна, когда вы закончили печать, вы должны уничтожить контекст устройства. Вы можете позволить деструктору объекта [CDC](../../mfc/reference/cdc-class.md) сделать это, или вы можете сделать это явно, позвонив [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).

## <a name="cwinappcwinapp"></a><a name="cwinapp"></a>CWinApp::CWinApp

Строит `CWinApp` объект и передает *lpszAppName* для хранения в качестве имени приложения.

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszAppName*<br/>
Строка с нулевым завершением, содержащая имя приложения, которое использует Windows. Если этот аргумент не поставляется `CWinApp` или является NULL, использует строку ресурса AFX_IDS_APP_TITLE или имя файла исполняемого файла.

### <a name="remarks"></a>Remarks

Вы должны построить один `CWinApp`глобальный объект вашего -производного класса. В приложении `CWinApp` может быть только один объект. Конструктор хранит указатель на `CWinApp` объект, `WinMain` чтобы можно было вызвать функции члена объекта для инициализации и запуска приложения.

## <a name="cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::DelRegTree

Удаляет определенный ключ реестра и все его подки.

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
Ручка к ключу реестра.

*strKeyName*<br/>
Имя ключа реестра, которое будет удалено.

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата ERROR_SUCCESS. Если функция выходит из строя, значение возврата является кодом ошибки ненулевого, определенным в Winerror.h.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы удалить указанный ключ и его подключи.

## <a name="cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::DoMessageBox

Платформа вызывает эту функцию участника для реализации ящика сообщений для глобальной функции [AfxMessageBox.](cstring-formatting-and-message-box-display.md#afxmessagebox)

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>Параметры

*lpszPrompt*<br/>
Адрес текста в почтовом ящике.

*nType*<br/>
[Стиль](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)коробки сообщений .

*nIDPrompt*<br/>
Индекс строки контекста Справка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает те же `AfxMessageBox`значения, что и .

### <a name="remarks"></a>Remarks

Не вызывайте эту функцию участника, чтобы открыть окно сообщений; вместо `AfxMessageBox` этого.

Переопределить эту функцию участника, чтобы настроить `AfxMessageBox` обработку вызовов в масштабах всего приложения.

## <a name="cwinappdowaitcursor"></a><a name="dowaitcursor"></a>CWinApp::DoWaitCursor

Эта функция члена называется рамочной для реализации [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), и [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>Параметры

*nКод*<br/>
Если этот параметр 1, появляется курсор ожидания. Если 0, курсор ожидания восстанавливается без приведения в число ссылок. Если -1, курсор ожидания заканчивается.

### <a name="remarks"></a>Remarks

По умолчанию реализует сятворник песочных часов. `DoWaitCursor`поддерживает подсчет ссылок. При положительном, песочные часы курсор отображается.

Хотя обычно вы не `DoWaitCursor` звоните напрямую, можно переопределить эту функцию участника, чтобы изменить курсора ожидания или сделать дополнительную обработку во время отображения курсора ожидания.

Для более простого и упорядоченного способа реализации `CWaitCursor`курсора ожидания используйте.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

## <a name="cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>CWinApp:EnableD2DSupport

Требуется Visual Studio 2010 с пакетом обновления 1 (SP1).

Позволяет прикладной поддержки D2D. Данный метод следует вызывать до инициализации основного окна.

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>Параметры

*d2dFactoryType*<br/>
Модель резьбы фабрики D2D и ресурсы, которые она создает.

*writeFactoryType*<br/>
Значение, описавававальное ли объект фабрики записи, будет общим или изолированным

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если поддержка D2D была включена, FALSE - в противном случае

## <a name="cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>CWinApp:EnableHtmlHelp

Вызовите эту функцию участника `CWinApp`изнутри конструктора вашего класса, чтобы использовать HTMLHelp для помощи приложения.

```cpp
void EnableHtmlHelp();
```

### <a name="remarks"></a>Remarks

## <a name="cwinappenableshellopen"></a><a name="enableshellopen"></a>CWinApp:EnableShellOpen

Вызовите эту функцию, как правило, с переопределения, `InitInstance` чтобы пользователи приложения могли открывать файлы данных, когда они дважды щелкнули файлами из windows File Manager.

```cpp
void EnableShellOpen();
```

### <a name="remarks"></a>Remarks

Позвоните `RegisterShellFileTypes` функции участника в сочетании с этой функцией, или предоставить . Файл REG с вашим заявлением на ручную регистрацию типов документов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

## <a name="cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarВзаимодействие

Обеспечивает взаимодействие панели задач.

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Уточняется, следует ли включено взаимодействие с панелью задач Windows 7 (TRUE) или отключено (FALSE).

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если взаимодействие панели задач может быть включено или отключено.

### <a name="remarks"></a>Remarks

Этот метод должен быть вызван до создания основного окна, в противном случае он утверждает и возвращает FALSE.

## <a name="cwinappexitinstance"></a><a name="exitinstance"></a>CWinApp::ExitInstance

Вызывается по системе `Run` из функции члена, чтобы выйти из этого экземпляра приложения.

```
virtual int ExitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Код выхода приложения; 0 указывает на отсутствие ошибок, а значения, превышающее 0, указывают на ошибку. Это значение используется в качестве `WinMain`значения возврата от .

### <a name="remarks"></a>Remarks

Не звоните в эту функцию `Run` участника из любого места, кроме как в функции участника.

Реализация этой функции по умолчанию записывает параметры фреймворка в приложение. Файл INI. Переопределить эту функцию для очистки, когда ваше приложение завершается.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

## <a name="cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationВосстановлениеПараметр

Извлекает параметр ввода для метода восстановления приложения.

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>Возвращаемое значение

Параметр ввода по умолчанию для метода восстановления приложения.

### <a name="remarks"></a>Remarks

Поведение этой функции по умолчанию возвращает NULL.

Для получения дополнительной информации [см. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).

## <a name="cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval

Возвращает время, в течение которого менеджер перезагрузки ждет возврата функции возврата.

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>Возвращаемое значение

Продолжительность времени в миллисекундах.

### <a name="remarks"></a>Remarks

Когда приложение, зарегистрированное с менеджером перезагрузки, неожиданно выходит из него, приложение пытается сохранить открытые документы и вызывает функцию обратного вызова. Функция обратного вызова по умолчанию — [CWinApp::ApplicationRecoveryCallback.](#applicationrecoverycallback)

Продолжительность времени, в течение которого фреймворк ждет возврата функции возврата, — это интервал пинга. Вы можете настроить интервал пинг, `CWinApp::GetApplicationRecoveryPingInterval` переопределяя `RegisterWithRestartManager`или предоставляя пользовательское значение для.

## <a name="cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags

Возвращает флаги для менеджера перезагрузки.

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>Возвращаемое значение

Флаги для менеджера перезагрузки. Реализация по умолчанию возвращает 0.

### <a name="remarks"></a>Remarks

Флаги для менеджера перезагрузки не влияют на реализацию по умолчанию. Они предусмотрены для использования в будущем.

Вы устанавливаете флаги при регистрации приложения у менеджера перезагрузки с помощью [CWinApp::RegisterWithRestartManager.](#registerwithrestartmanager)

Возможные значения для флагов менеджера перезагрузки следующие:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>CWinApp:GetAppRegistryKey

Возвращает ключ для\\HKEY_CURRENT_USER "Программное обеспечение",RegistryKey-ProfileName.

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ приложения, если функция успешно; в противном случае NULL.

### <a name="remarks"></a>Remarks

## <a name="cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler

Получает обработчик восстановления данных для данного экземпляра приложения.

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>Возвращаемое значение

Обработчик восстановления данных для данного экземпляра приложения.

### <a name="remarks"></a>Remarks

Каждое приложение, использующее менеджер перезагрузки, должно иметь один экземпляр [класса CDataRecoveryHandler.](../../mfc/reference/cdatarecoveryhandler-class.md) Этот класс отвечает за мониторинг открытых документов и автосохранения файлов. Поведение диспетчера `CDataRecoveryHandler` зависит от конфигурации менеджера перезагрузки. Для получения дополнительной [CDataRecoveryHandler Class](../../mfc/reference/cdatarecoveryhandler-class.md)информации см.

Этот метод возвращает NULL на операционные системы раньше, чем Windows Vista. Менеджер перезагрузки не поддерживается на операционных системах раньше, чем Windows Vista.

Если в настоящее время в приложении нет обработчика восстановления данных, этот метод создает его и возвращает указатель к нему.

## <a name="cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition

Получает позицию первого шаблона документа в приложении.

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

### <a name="remarks"></a>Remarks

Используйте значение POSITION, возвращенное в вызове [GetNextDocTemplate,](#getnextdoctemplate) чтобы получить первый объект [CDocTemplate.](../../mfc/reference/cdoctemplate-class.md)

## <a name="cwinappgethelpmode"></a><a name="gethelpmode"></a>CWinApp:GetHelpMode

Извлекает тип справки, используемой приложением.

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>Возвращаемое значение

Тип справки, используемый приложением. Смотрите [CWinApp::m_eHelpType](#m_ehelptype) для получения дополнительной информации.

## <a name="cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate

Получает шаблон документа, идентифицированный *pos,* затем устанавливает *pos* к значению POSITION.

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Ссылка на значение POSITION, возвращенное предыдущим вызовом `GetNextDocTemplate` или [GetFirstDocTemplatePosition.](#getfirstdoctemplateposition) Значение обновляется до следующей позиции этим вызовом.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CDocTemplate.](../../mfc/reference/cdoctemplate-class.md)

### <a name="remarks"></a>Remarks

Вы можете `GetNextDocTemplate` использовать в цикле передних итерации, если `GetFirstDocTemplatePosition`установить исходное положение с вызовом.

Вы должны убедиться, что значение POSITION является действительным. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный шаблон документа является последним доступным, то новое значение *pos* устанавливается в NULL.

## <a name="cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults

Вызовите эту функцию участника, чтобы подготовить контекст устройства принтера для печати.

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>Параметры

*pPrintDlg*<br/>
Указатель на структуру [PRINTDLG.](/windows/win32/api/commdlg/ns-commdlg-printdlga)

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Извлекает текущие по умолчанию принтера из Windows. Файл INI по мере необходимости или последняя конфигурация принтера, установленная пользователем в настройке печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

## <a name="cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>CWinApp:GetProfileBinary

Позвоните в эту функцию участника, чтобы получить двоичные данные из записи в определенном разделе реестра приложения или . Файл INI.

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись.

*lpszEntry*<br/>
Очки строке с нулевым завершением, содержащей значение записи, значение которой должно быть извлечено.

*ppData*<br/>
Указывает указатель на указатель, который получит адрес данных.

*pBytes*<br/>
Очки UINT, который будет получать размер данных (в байтах).

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена не является чувствительной к случаю, поэтому строки в параметрах *lpszSection* и *lpszEntry* могут отличаться в случае.

> [!NOTE]
> `GetProfileBinary`выделяет буфер и возвращает свой \* адрес в *ppData*. Звонящий несет ответственность за освобождение буфера с помощью **удаления.**

> [!IMPORTANT]
> Данные, возвращенные этой функцией, не обязательно NULL прекращаются, и абонент должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

Для дополнительного примера см. [CWinApp::WriteProfileBinary](#writeprofilebinary).

## <a name="cwinappgetprofileint"></a><a name="getprofileint"></a>CWinApp:GetProfileInt

Позвоните в эту функцию участника, чтобы получить значение рядового из записи в определенном разделе реестра приложения или . Файл INI.

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись.

*lpszEntry*<br/>
Очки строке с нулевым завершением, содержащей значение записи, значение которой должно быть извлечено.

*nДефолт*<br/>
Упогоняет значение по умолчанию для возврата, если фреймворк не может найти запись.

### <a name="return-value"></a>Возвращаемое значение

Значение всей строки, следующей за указанной записью, если функция успешна. Значение возврата — это значение параметра *nDefault,* если функция не находит запись. Значение возврата составляет 0, если значение, которое соответствует указанному входу, не является рядом.

Эта функция члена поддерживает гексадецимальную нотацию для значения в . Файл INI. При получении подписанного стыковки следует бросить значение в **int.**

### <a name="remarks"></a>Remarks

Эта функция члена не является чувствительной к случаю, поэтому строки в параметрах *lpszSection* и *lpszEntry* могут отличаться в случае.

> [!IMPORTANT]
> Данные, возвращенные этой функцией, не обязательно NULL прекращаются, и абонент должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

Для дополнительного примера см. [CWinApp::WriteProfileInt](#writeprofileint).

## <a name="cwinappgetprofilestring"></a><a name="getprofilestring"></a>CWinApp:GetProfileString

Вызов эту функцию участника, чтобы получить строку, связанную с записью в указанном разделе в реестре приложения или . Файл INI.

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись.

*lpszEntry*<br/>
Указывает на нулевую строку, содержащую строку, строка которой должна быть извлечена. Это значение не должно быть NULL.

*lpszDefault*<br/>
Указывает на значение строки по умолчанию для данной записи, если запись не может быть найдена в файле инициализации.

### <a name="return-value"></a>Возвращаемое значение

Значение возврата — строка из приложения. Файл INI или *lpszDefault,* если строка не может быть найдена. Максимальная длина строки, поддерживаемая платформой, _MAX_PATH. Если *lpszDefault* является NULL, значение возврата является пустой строкой.

### <a name="remarks"></a>Remarks

> [!IMPORTANT]
> Данные, возвращенные этой функцией, не обязательно NULL прекращаются, и абонент должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Для другого примера см. пример [для CWinApp:GetProfileInt](#getprofileint).

## <a name="cwinappgetsectionkey"></a><a name="getsectionkey"></a>CWinApp::GetSectionKey

Возвращает ключ для\\HKEY_CURRENT_USER "Программное обеспечение".

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Название ключа, которое необходимо получить.

*Ptm*<br/>
Указатель на `CAtlTransactionManager` объект.

### <a name="return-value"></a>Возвращаемое значение

Ключ раздела если функция успешно; в противном случае NULL.

### <a name="remarks"></a>Remarks

## <a name="cwinapphideapplication"></a><a name="hideapplication"></a>CWinApp::HideApplication

Позвоните этой функции участника, чтобы скрыть приложение перед закрытием открытых документов.

```cpp
void HideApplication();
```

## <a name="cwinapphtmlhelp"></a><a name="htmlhelp"></a>CWinApp::HtmlHelp

Вызовите эту функцию участника, чтобы вызвать приложение HTMLHelp.

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>Параметры

*dwData*<br/>
Определяет дополнительные данные. Используемое значение зависит от значения параметра *nCmd.* По умолчанию, к которому `0x000F` [HH_HELP_CONTEXT](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command).

*nCmd*<br/>
Задает тип запрошенной справки. Список возможных значений и то, как они влияют на параметр *dwData,* см. параметр *uCommand,* описанный в функциях [HtmlHelpW](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw) или [HtmlHelpA](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa) API в SDK Windows.

### <a name="remarks"></a>Remarks

Платформа также вызывает эту функцию для вызова приложения HTMLHelp.

Платформа автоматически закроет приложение HTMLHelp, когда ваше приложение будет закрыто.

## <a name="cwinappinitinstance"></a><a name="initinstance"></a>CWinApp::InitInstance

Windows позволяет несколько копий одной и той же программы для запуска в то же время.

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если инициализация является успешной; в противном случае 0.

### <a name="remarks"></a>Remarks

Инициализация приложения концептуально разделена на два раздела: одноразовая инициализация приложения, которая выполняется при первом запуске программы, и инициализация экземпляра, которая выполняется каждый раз, когда выполняется копия программы, включая первый раз. Реализация фреймворка `WinMain` вызывает эту функцию.

Переопределить `InitInstance` для инициализации каждого нового экземпляра приложения, работаемого под Windows. Как правило, `InitInstance` переопределение для построения `CWinThread::m_pMainWnd` основного объекта окна и установки члена данных для указать на это окно. Для получения дополнительной информации о переопределение этой функции участника, [см. CWinApp: Класс приложений](../../mfc/cwinapp-the-application-class.md).

> [!NOTE]
> Приложения МФЦ должны быть инициализированы как одноразовая квартира (STA). Если вы звоните [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) в переопределении, `InitInstance` укажите COINIT_APARTMENTTHREADED (а не COINIT_MULTITHREADED).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

## <a name="cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarВзаимодействие

Сообщает, включено ли взаимодействие панели задач Windows 7.

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если `EnableTaskbarInteraction` был вызван и операционная система Windows 7 или выше.

### <a name="remarks"></a>Remarks

Взаимодействие панели задач означает, что приложение MDI отображает содержимое детей MDI в отдельных эскизах с вкладками, которые появляются, когда указатель мыши находится над кнопкой панели задач приложения.

## <a name="cwinapploadcursor"></a><a name="loadcursor"></a>CWinApp::LoadCursor

Загружает ресурс курсора, названный *lpszResourceName* или указанный *nIDResource,* из текущего исполняемого файла.

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указывает на нулевую строку, содержащую имя ресурса курсора. Вы можете `CString` использовать для этого аргумента.

*nIDResource*<br/>
Идентификатор ресурса курсора. Список ресурсов можно узнать в [SDK](/windows/win32/api/winuser/nf-winuser-loadcursorw) Windows.

### <a name="return-value"></a>Возвращаемое значение

Ручка курсора в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

`LoadCursor`загружает курсор в память только в том случае, если он не был ранее загружен; в противном случае он получает ручку существующего ресурса.

Используйте функцию [члена LoadStandardCursor](#loadstandardcursor) или [LoadOEMCursor](#loadoemcursor) для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

## <a name="cwinapploadicon"></a><a name="loadicon"></a>CWinApp::LoadIcon

Загружает ресурс значка, названный *lpszResourceName* или указанный *nIDResource,* из исполняемого файла.

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указывает на нулевую строку, содержащую имя ресурса значка. Вы также можете `CString` использовать для этого аргумента.

*nIDResource*<br/>
Идентификационный номер ресурса значок.

### <a name="return-value"></a>Возвращаемое значение

Ручка к значку в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

`LoadIcon`загружает значок только в том случае, если он не был загружен ранее; в противном случае он получает ручку существующего ресурса.

Для доступа к предопределенным значкам Windows можно использовать функцию участника [LoadStandardIcon](#loadstandardicon) или [LoadOEMIcon.](#loadoemicon)

> [!NOTE]
> Эта функция-член вызывает функцию In32 API [LoadIcon,](/windows/win32/api/winuser/nf-winuser-loadiconw)которая может загружать только значок, размер которого соответствует SM_CXICON и SM_CYICON значениями метрики системы.

## <a name="cwinapploadoemcursor"></a><a name="loadoemcursor"></a>CWinApp::LoadOEMCursor

Загружает предопределенный ресурс курсора Windows, указанный *nIDCursor.*

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>Параметры

*nIDCursor*<br/>
**OCR_** манифест постоянного идентификатора, который определяет предопределенный курсор Windows. Вы должны `#define OEMRESOURCE` `#include \<afxwin.h>` иметь, прежде чем получить доступ к **OCR_** констант в WINDOWS. H.

### <a name="return-value"></a>Возвращаемое значение

Ручка курсора в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Используйте `LoadOEMCursor` функцию или [функцию члена LoadStandardCursor](#loadstandardcursor) для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

## <a name="cwinapploadoemicon"></a><a name="loadoemicon"></a>CWinApp::LoadOEMIcon

Загружает предопределенный ресурс значка Windows, указанный *nIDIcon.*

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>Параметры

*nIDIcon*<br/>
**В OIC_** манифест постоянного идентификатора, который определяет предопределенный значок Windows. Вы должны `#define OEMRESOURCE` `#include \<afxwin.h>` иметь доступ к **OIC_** констант в WINDOWS. H.

### <a name="return-value"></a>Возвращаемое значение

Ручка к значку в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Используйте `LoadOEMIcon` функцию или функцию [участника LoadStandardIcon](#loadstandardicon) для доступа к предопределенным значкам Windows.

## <a name="cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>CWinApp:LoadStandardCursor

Загружает предопределенный ресурс курсора Windows, который определяет *lpszCursorName.*

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>Параметры

*lpszCursorName*<br/>
**IDC_** манифест постоянного идентификатора, который определяет предопределенный курсор Windows. Эти идентификаторы определены в WINDOWS. H. В следующем списке показаны возможные предопределенные значения и значения для *lpszCursorName*:

- IDC_ARROW стандартный курсор стрелки

- IDC_IBEAM Стандартный курсор текста

- IDC_WAIT курсор песочных часов, используемый при выполнении Windows трудоемкой задачи

- IDC_CROSS курсор перекрестного волоса для выбора

- IDC_UPARROW Стрелка, которая указывает прямо вверх

- IDC_SIZE Устаревшие и неподдерживаемые; использовать IDC_SIZEALL

- IDC_SIZEALL четырехконечная стрелка. Курсор для использования для замены окна.

- IDC_ICON Устаревшие и неподдерживаемые. Используйте IDC_ARROW.

- IDC_SIZENWSE двуглавая стрелка с концами в левом верхнем и нижнем правом

- IDC_SIZENESW двуглавая стрелка с концами в правом верхнем и нижнем левом

- IDC_SIZEWE Горизонтальная двуглавая стрелка

- IDC_SIZENS Вертикальная двуглавая стрелка

### <a name="return-value"></a>Возвращаемое значение

Ручка курсора в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Используйте `LoadStandardCursor` функцию или [функцию члена LoadOEMCursor](#loadoemcursor) для доступа к предопределенным курсорам Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

## <a name="cwinapploadstandardicon"></a><a name="loadstandardicon"></a>CWinApp:LoadStandardIcon

Загружает предопределенный ресурс значка Windows, который определяет *lpszIconName.*

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>Параметры

*lpszIconName*<br/>
Явный постоянный идентификатор, определяемый к предопределенному значку Windows. Эти идентификаторы определены в WINDOWS. H. Список возможных предопределенных значений и их описания можно узнать *в* loadIcon в [SDK](/windows/win32/api/winuser/nf-winuser-loadiconw) Windows.

### <a name="return-value"></a>Возвращаемое значение

Ручка к значку в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Remarks

Используйте `LoadStandardIcon` функцию участника или [LoadOEMIcon](#loadoemicon) для доступа к предопределенным значкам Windows.

## <a name="cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings

Вызовите эту функцию участника из функции члена [InitInstance,](#initinstance) чтобы включить и загрузить список самых последних используемых (MRU) файлов и последнее состояние предварительного просмотра.

```cpp
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>Параметры

*nMaxMRU*<br/>
Количество недавно используемых файлов для отслеживания.

### <a name="remarks"></a>Remarks

Если *nMaxMRU* равен 0, список MRU не будет сохранен.

## <a name="cwinappm_bhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode

TRUE, если приложение находится в контексте справки режиме (обычно вызывается с SHIFT и F1); в противном случае FALSE.

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Remarks

В контексте справки курсор становится вопросительным знаком, и пользователь может перемещать его по экрану. Изучите этот флаг, если вы хотите реализовать специальную обработку, когда в режиме справки. `m_bHelpMode`является публичной переменной типа BOOL.

## <a name="cwinappm_dwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags

Флаги, определяющие, как ведет себя менеджер перезагрузки.

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Remarks

Чтобы включить менеджер перезагрузки, установите `m_dwRestartManagerSupportFlags` поведение, которое вы хотите. В следующей таблице показаны доступные флаги.

|||
|-|-|
|Флаг|Описание|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|Приложение зарегистрировано с помощью [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Менеджер перезагрузки отвечает за перезагрузку приложения, если оно неожиданно выходит из него.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|Приложение зарегистрировано у менеджера перезагрузки, и менеджер перезагрузки вызывает функцию возврата вызова при перезагрузке приложения. Функция обратного вызова по умолчанию — [CWinApp::ApplicationRecoveryCallback.](#applicationrecoverycallback)|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|Автосохранение включено, и менеджер перезагрузки автоматически сохраняет все открытые документы при перезагрузке приложения.|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|Автосавеж включен, и менеджер перезагрузки регулярно сохраняет все открытые документы. Интервал определяется [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|Менеджер перезагрузки открывает ранее открытые документы после перезапуска приложения с неожиданного выхода. [Класс CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) обрабатывает хранение списка открытых документов и их восстановление.|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|Менеджер перезагрузки предлагает пользователю восстановить автоматически сохраненные файлы после перезагрузки приложения. Класс `CDataRecoveryHandler` запрашивает пользователя.|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|Союз AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_SUPPORT_RECOVER и AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|Объединение AFX_RESTART_MANAGER_SUPPORT_RESTART, AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|Профсоюз ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY, AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL, AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES и AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES.|

## <a name="cwinappm_ehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType

Тип этого члена данных — это перечисленный тип AFX_HELP_TYPE, `CWinApp` который определяется в классе.

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Remarks

Перечисление AFX_HELP_TYPE определяется следующим образом:

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- Чтобы настроить справку приложения в HTML Help, позвоните [в SetHelpMode](#sethelpmode) и укажите. `afxHTMLHelp`

- Чтобы настроить справку приложения на WinHelp, позвоните `SetHelpMode` и укажите. `afxWinHelp`

## <a name="cwinappm_hinstance"></a><a name="m_hinstance"></a>CWinApp::m_hInstance

Соответствует параметру *hInstance,* передаваемому Windows. `WinMain`

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Remarks

Член `m_hInstance` данных — это ручка текущего экземпляра приложения, работающегося под Windows. Это возвращается глобальной функцией [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance`является публичной переменной типа HINSTANCE.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

## <a name="cwinappm_lpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine

Соответствует параметру *lpCmdLine,* передаваемому `WinMain`Windows.

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Remarks

Указывает на нулевую строку, определяющую командную строку для приложения. Используйте `m_lpCmdLine` для доступа к любым аргументам командной строки, которые пользователь ввел при начале работы приложения. `m_lpCmdLine`является публичной переменной типа LPTSTR.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappm_nautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval

Продолжительность времени в миллисекундах между автосавами.

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Remarks

Вы можете настроить менеджер перезагрузки для автоматического сохранения открытых документов через заданные интервалы. Если приложение не автоматически сохраняет файлы, этот параметр не имеет эффекта.

## <a name="cwinappm_ncmdshow"></a><a name="m_ncmdshow"></a>CWinApp::m_nCmdShow

Соответствует параметру *nCmdShow,* передаваемому `WinMain`Windows.

```
int m_nCmdShow;
```

### <a name="remarks"></a>Remarks

Вы должны `m_nCmdShow` пройти в качестве аргумента, когда вы звоните [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) для основного окна приложения. `m_nCmdShow`является публичной переменной типа **Int**.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

## <a name="cwinappm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd

Используйте этот участник данных для хранения указателя на основное окно контейнерного приложения OLE, в результате которого активировано серверное приложение OLE.

### <a name="remarks"></a>Remarks

Если этот участник данных является NULL, приложение не является активным.

Рамочная система устанавливает эту переменную члена, когда окно кадра находится на месте, активированном контейнерным приложением OLE.

## <a name="cwinappm_pdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler

Указатель на обработчик восстановления данных для приложения.

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Remarks

Обработчик восстановления данных приложения отслеживает открытые документы и аутосохраняет их. Платформа использует обработчик восстановления данных для восстановления автоматически сохраненных файлов при перезапуске приложения после неожиданного выхода. Для получения дополнительной [CDataRecoveryHandler Class](../../mfc/reference/cdatarecoveryhandler-class.md)информации см.

## <a name="cwinappm_pszappname"></a><a name="m_pszappname"></a>CWinApp::m_pszAppName

Указывает имя приложения.

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Remarks

Имя приложения может исходить от параметра, передаваемого конструктору [CWinApp,](#cwinapp) или, если не указано, на строку ресурса с идентификатором AFX_IDS_APP_TITLE. Если имя приложения не найдено в ресурсе, оно исходит от программы . EXE имя файла.

Возвращается глобальной функцией [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName`является публичной переменной типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если вы назначаете `m_pszAppName`значение, оно должно быть динамически распределено на куче. Деструктор `CWinApp` вызывает **свободно**() с этим указателем. Вы многие хотите `_tcsdup`использовать функцию библиотеки выполнения времени, чтобы сделать выделение. Кроме того, освободите память, связанную с текущим указателем, перед назначением нового значения. Пример:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

## <a name="cwinappm_pszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName

Содержит имя исполняемого файла приложения без расширения.

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Remarks

В отличие от [m_pszAppName,](#m_pszappname)это имя не может содержать пробелы. `m_pszExeName`является публичной переменной типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если вы назначаете `m_pszExeName`значение, оно должно быть динамически распределено на куче. Деструктор `CWinApp` вызывает **свободно**() с этим указателем. Вы многие хотите `_tcsdup`использовать функцию библиотеки выполнения времени, чтобы сделать выделение. Кроме того, освободите память, связанную с текущим указателем, перед назначением нового значения. Пример:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

## <a name="cwinappm_pszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath

Содержит путь к файлу справки приложения.

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Remarks

По умолчанию, фреймворк инициализирует `m_pszHelpFilePath` название приложения с ". HLP" приложено. Чтобы изменить имя файла справки, установите `m_pszHelpFilePath` точку строки, содержащей полное имя желаемого файла справки. Удобное место для этого находится в функции [InitInstance](#initinstance) приложения. `m_pszHelpFilePath`является публичной переменной типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если вы назначаете `m_pszHelpFilePath`значение, оно должно быть динамически распределено на куче. Деструктор `CWinApp` вызывает **свободно**() с этим указателем. Вы многие хотите `_tcsdup`использовать функцию библиотеки выполнения времени, чтобы сделать выделение. Кроме того, освободите память, связанную с текущим указателем, перед назначением нового значения. Пример:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

## <a name="cwinappm_pszprofilename"></a><a name="m_pszprofilename"></a>CWinApp::m_pszProfileName

Содержит название приложения . Файл INI.

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Remarks

`m_pszProfileName`является публичной переменной типа **const char**<strong>\*</strong>.

> [!NOTE]
> Если вы назначаете `m_pszProfileName`значение, оно должно быть динамически распределено на куче. Деструктор `CWinApp` вызывает **свободно**() с этим указателем. Вы многие хотите `_tcsdup`использовать функцию библиотеки выполнения времени, чтобы сделать выделение. Кроме того, освободите память, связанную с текущим указателем, перед назначением нового значения. Пример:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

## <a name="cwinappm_pszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey

Используется для определения того, где в реестре или файле INI хранятся настройки профиля приложения.

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Remarks

Как правило, этот участник данных рассматривается как только для чтения.

- Значение хранится в ключе реестра. Название для настройки профиля приложения прилагается к следующему ключу реестра: HKEY_CURRENT_USER/Software/LocalAppWizard-Generated/.

Если вы назначаете `m_pszRegistryKey`значение, оно должно быть динамически распределено на куче. Деструктор `CWinApp` вызывает **свободно**() с этим указателем. Вы многие хотите `_tcsdup`использовать функцию библиотеки выполнения времени, чтобы сделать выделение. Кроме того, освободите память, связанную с текущим указателем, перед назначением нового значения. Пример:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

## <a name="cwinappm_pszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID

Идентификатор модели пользователя приложения.

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Remarks

## <a name="cwinapponcontexthelp"></a><a name="oncontexthelp"></a>CWinApp::OnContextHelp

Ручки справки SHIFT-F1 в приложении.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса, а также добавить запись таблицы акселератора, обычно SHIFT-F1.

`OnContextHelp`помещает приложение в режим справки. Курсор изменяется на стрелку и вопросительный знак, и пользователь может переместить указатель мыши и нажать левую кнопку мыши, чтобы выбрать диалоговую кнопку, окно, меню или кнопку команды. Эта функция члена получает контекст справки объекта под курсором и вызывает функцию Windows WinHelp с этим контекстом справки.

## <a name="cwinapponddecommand"></a><a name="onddecommand"></a>CWinApp::OnDDECommand

Вызывается системой, когда основное окно кадра получает сообщение DDE-выполнения.

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>Параметры

*lpszCommand*<br/>
Очки на строку команды DDE, полученные приложением.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если команда обработана; в противном случае 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию проверяет, является ли команда запросом на открытие документа, и, если да, то открывает указанный документ. Менеджер файлов Windows обычно отправляет такие строки команды DDE, когда пользователь дважды щелкает файл данных. Переопределить эту функцию для обработки других команд выполнения DDE, таких как команда для печати.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

## <a name="cwinapponfilenew"></a><a name="onfilenew"></a>CWinApp::OnFileNew

Реализует команду ID_FILE_NEW.

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_FILE_NEW, OnFileNew )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если включена, эта функция обрабатывает выполнение команды Файл Новый.

См [Технический примечание 22](../../mfc/tn022-standard-commands-implementation.md) для получения информации о поведении по умолчанию и руководства о том, как переопределить эту функцию участника.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileopen"></a><a name="onfileopen"></a>CWinApp::OnFileOpen

Реализует команду ID_FILE_OPEN.

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если включена, эта функция обрабатывает выполнение команды File Open.

Для получения информации о поведении по умолчанию и рекомендаций по тому, как переопределить эту функцию участника, [см.](../../mfc/tn022-standard-commands-implementation.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup

Реализует команду ID_FILE_PRINT_SETUP.

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если включена, эта функция обрабатывает выполнение команды типографии файла.

Для получения информации о поведении по умолчанию и рекомендаций по тому, как переопределить эту функцию участника, [см.](../../mfc/tn022-standard-commands-implementation.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponhelp"></a><a name="onhelp"></a>CWinApp::OnHelp

Обрабатывает справку F1 в приложении (с использованием текущего контекста).

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Remarks

Обычно вы также добавите акселератор-ключ запись для ключа F1. Включение ключа F1 является лишь конвенцией, а не требованием.

Для включения `ON_COMMAND( ID_HELP, OnHelp )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если включен, называется рамочой, когда пользователь нажимает на ключ F1.

Реализация этой функции обработчика сообщений по умолчанию определяет контекст справки, соответствующий текущему окну, диалоговому окну или элементу меню, а затем вызывает WINHELP. Exe. Если в настоящее время нет контекста, функция использует контекст по умолчанию.

Переопределить эту функцию участника, чтобы настроить контекст справки на нечто иное, чем окно, диалоговое окно, элемент меню или кнопку панели инструментов, которая в настоящее время находится в центре внимания. Вызов `WinHelp` с желаемым идентификатором контекста Справки.

## <a name="cwinapponhelpfinder"></a><a name="onhelpfinder"></a>CWinApp::OnHelpFinder

Обрабатывает ID_HELP_FINDER и ID_DEFAULT_HELP команды.

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если функция включена, фреймворк вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает команду Help Finder для вызова `WinHelp` стандартной **HELP_FINDER** темы.

## <a name="cwinapponhelpindex"></a><a name="onhelpindex"></a>CWinApp::Хелпиндекс

Обрабатывает ID_HELP_INDEX команду и предоставляет тему справки по умолчанию.

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Если функция включена, фреймворк вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает команду «Индекс справки» для вызова `WinHelp` стандартной **HELP_INDEX** темы.

## <a name="cwinapponhelpusing"></a><a name="onhelpusing"></a>CWinApp::OnHelpUsing

Обрабатывает команду ID_HELP_USING.

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Remarks

Для включения `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` этой функции участника необходимо добавить заявление на карту сообщений `CWinApp` класса. Платформа вызывает эту функцию обработчика сообщений, когда пользователь приложения выбирает `WinHelp` команду «Помощь» для вызова приложения со стандартной **темой HELP_HELPONHELP.**

## <a name="cwinapponidle"></a><a name="onidle"></a>CWinApp::Onidle

Переизбь эту функцию участника для выполнения обработки простоя.

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>Параметры

*lCount*<br/>
Счетчик с шагом каждый `OnIdle` раз вызывается, когда очередь сообщений приложения пуста. Этот отсчет сбросить до 0 каждый раз, когда обрабатывается новое сообщение. Параметр *lCount* можно использовать для определения относительного времени простоя приложения без обработки сообщения.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, чтобы получить больше времени простоя обработки; 0, если больше не требуется время простоя.

### <a name="remarks"></a>Remarks

`OnIdle`вызывается в цикле сообщения по умолчанию, когда очередь сообщений приложения пуста. Используйте переопределение, чтобы вызвать свои собственные фоновые задачи обработчика простоя.

`OnIdle`должны вернуть 0, чтобы указать, что время простоя обработки не требуется. Параметр *lCount* приращен каждый раз `OnIdle` вызывается, когда очередь сообщений пуста и сбрасывается до 0 каждый раз, когда новое сообщение обрабатывается. Вы можете вызвать различные процедуры простоя на основе этого подсчета.

Ниже приводится краткое обобщение обработки циклов простоя:

1. Если цикл сообщений в библиотеке класса Microsoft Foundation проверяет очередь `OnIdle` сообщений и не находит ожидающих сообщений, он требует объект приложения и поставляет 0 в качестве аргумента *lCount.*

2. `OnIdle`выполняет некоторую обработку и возвращает ненулевое значение, чтобы указать, что оно должно быть вызвано снова, чтобы сделать дальнейшую обработку.

3. Цикл сообщения снова проверяет очередь сообщений. Если сообщения не ожидаются, он вызывает `OnIdle` снова, приравня аргумент *lCount.*

4. В `OnIdle` конце концов, завершает обработку всех своих задач простоя и возвращает 0. Это говорит циклу сообщения `OnIdle` прекратить вызов до тех пор, пока следующее сообщение не будет получено из очереди сообщений, после чего цикл простоя перезапускается с аргументом, установленным на 0.

Не выполняйте длительные задачи, `OnIdle` так как `OnIdle` приложение не может обрабатывать пользовательский вход до возвращения.

> [!NOTE]
> Реализация обновлений `OnIdle` командных объектов пользовательского интерфейса, таких как элементы меню и кнопки панели инструментов, выполняет внутреннюю очистку структуры данных. Поэтому, если вы `OnIdle`переопределяете, вы должны позвонить `CWinApp::OnIdle` с `lCount` переопределенной версией. Сначала позвоните во все данные простоя базового класса (т.е. до тех пор, пока базовый класс `OnIdle` не вернется 0). Если вам нужно выполнить работу до завершения обработки базового класса, просмотрите реализацию базового класса, чтобы выбрать подходящий *lCount,* в течение которого выполнить свою работу.

Если вы не `OnIdle` хотите, чтобы вас вызывали всякий раз, когда сообщение извлекается из очереди сообщений, вы можете переопределить [CWinThreadIsIdleMessage.](../../mfc/reference/cwinthread-class.md#isidlemessage) Если приложение установило очень короткий таймер, или если система `OnIdle` отправляет WM_SYSTIMER сообщение, то будет вызываться повторно, и ухудшать производительность.

### <a name="example"></a>Пример

Следующие два примера `OnIdle`показывают, как использовать . Первый пример обрабатывает две задачи простоя, используя аргумент *lCount* для определения приоритетов задач. Первая задача является приоритетной задачей, и вы должны делать это, когда это возможно. Вторая задача менее важна и должна быть выполнена только при длительной паузе в входе пользователя. Обратите внимание на вызов в `OnIdle`версию базового класса . Второй пример управляет группой простаивающих задач с различными приоритетами.

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

## <a name="cwinappopendocumentfile"></a><a name="opendocumentfile"></a>CWinApp::OpenDocumentFile

Платформа называет этот метод, чтобы открыть названный файл [CDocument](../../mfc/reference/cdocument-class.md) для приложения.

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszFileName*<br/>
(в) Имя файла, которое будет открыто.

*bAddToMRU*<br/>
(в) TRUE указывает на то, что документ является одним из самых последних файлов; FALSE указывает, что документ не является одним из последних файлов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CDocument` если успешно; в противном случае NULL.

### <a name="remarks"></a>Remarks

Если документ с этим именем уже открыт, первое окно кадра, содержащее этот документ, получит фокус. Если приложение поддерживает несколько шаблонов документов, шаблон использует расширение имени файла, чтобы найти соответствующий шаблон документа, чтобы попытаться загрузить документ. В случае успеха шаблон документа создает окно кадра и представление для документа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::ParseCommandLine

Вызов исчерпайте эту функцию участника, чтобы разобрать командную строку и отправить параметры, по одному, на [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).

```cpp
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*rCmdInfo*<br/>
Ссылка на объект [CCommandLineInfo.](../../mfc/reference/ccommandlineinfo-class.md)

### <a name="remarks"></a>Remarks

При запуске нового проекта MFC с помощью Мастера Приложения Мастер `CCommandLineInfo`приложения создаст локальный экземпляр, а затем вызовет `ProcessShellCommand` и `ParseCommandLine` в функции члена [InitInstance.](#initinstance) Командная строка следует за маршрутом, описанным ниже:

1. После создания `InitInstance`в, `CCommandLineInfo` объект передается `ParseCommandLine`.

2. `ParseCommandLine`затем `CCommandLineInfo::ParseParam` вызывает повторно, один раз для каждого параметра.

3. `ParseParam`заполняет `CCommandLineInfo` объект, который затем передается [ProcessShellCommand.](#processshellcommand)

4. `ProcessShellCommand`обрабатывает аргументы и флаги командной строки.

Обратите внимание, `ParseCommandLine` что вы можете звонить непосредственно по мере необходимости.

Для описания флагов командной строки см. [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).

## <a name="cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>CWinApp::PreTranslateMessage

Переизбь эту функцию для фильтрации оконных сообщений перед отправкой на функции Windows [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) `CWinApp::PreTranslateMessage` Реализация по умолчанию выполняет перевод клавиша акселератора, поэтому вы должны вызвать функцию участника в перезаверченной версии.

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*pMsg*<br/>
Указатель на структуру [MSG,](/windows/win32/api/winuser/ns-winuser-msg) содержащую сообщение для обработки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение было `PreTranslateMessage` полностью обработано и не должно обрабатываться дальше. Ноль, если сообщение должно быть обработано в обычном режиме.

## <a name="cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter

Функция крючка платформы вызывает эту функцию участника для фильтрации и реагирования на определенные сообщения Windows.

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>Параметры

*code*<br/>
Определяет код крючка. Эта функция члена использует код для определения того, как обрабатывать *lpMsg.*

*lpMsg*<br/>
Указатель на промежутке Windows [MSG.](/windows/win32/api/winuser/ns-winuser-msg)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если сообщение обработано; в противном случае 0.

### <a name="remarks"></a>Remarks

Функция крючка обрабатывает события перед их отправкой на обычную обработку сообщений приложения.

Если вы переопределяете эту расширенную функцию, обязательно позвоните в версию базового класса для поддержания обработки крючка.

## <a name="cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::ProcessShellCommand

Эта функция участника вызывается [InitInstance](#initinstance) для принятия `CCommandLineInfo` параметров, передаваемых с объекта, идентифицированного *rCmdInfo,* и выполнения указанного действия.

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>Параметры

*rCmdInfo*<br/>
Ссылка на объект [CCommandLineInfo.](../../mfc/reference/ccommandlineinfo-class.md)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если команда оболочки успешно обработана. Если 0, возвращайтесь FALSE из [InitInstance](#initinstance).

### <a name="remarks"></a>Remarks

При запуске нового проекта MFC с помощью Мастера Приложения Мастер `CCommandLineInfo`приложения создаст локальный экземпляр, а затем вызовет `ProcessShellCommand` и [ParseCommandLine](#parsecommandline) в функции `InitInstance` участника. Командная строка следует за маршрутом, описанным ниже:

1. После создания `InitInstance`в, `CCommandLineInfo` объект передается `ParseCommandLine`.

2. `ParseCommandLine`затем вызывает [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) повторно, раз для каждого параметра.

3. `ParseParam`заполняет `CCommandLineInfo` объект, который затем `ProcessShellCommand`передается.

4. `ProcessShellCommand`обрабатывает аргументы и флаги командной строки.

Члены данных `CCommandLineInfo` объекта, идентифицированные [CCommandLineInfo::m_nShellCommand,](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)имеют следующий перечисленный тип, `CCommandLineInfo` который определяется в классе.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

Краткое описание каждого из этих значений см. `CCommandLineInfo::m_nShellCommand`

## <a name="cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinApp::ProcessWndProcException

Платформа вызывает эту функцию элемента всякий раз, когда обработчик не улавливают исключение, брошенное в одном из сообщений приложения или обработчиков команд.

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>Параметры

*E*<br/>
Указатель на непойманное исключение.

*pMsg*<br/>
Проницательная система [MSG,](/windows/win32/api/winuser/ns-winuser-msg)содержащая информацию о сообщении Windows, из-за которого фреймворк может выбросить исключение.

### <a name="return-value"></a>Возвращаемое значение

Значение, которое должно быть возвращено в Windows. Обычно это 0L для сообщений windows, 1L (правда) для сообщений команд.

### <a name="remarks"></a>Remarks

Не вызывайте эту функцию участника напрямую.

Реализация этой функции участника по умолчанию создает окно сообщений. Если непойманное исключение возникает при сбое команды меню, панели инструментов или команды ускорителя, в поле сообщения отображается сообщение "Командование не удалось"; в противном случае отображается сообщение "Внутренняя ошибка приложения".

Переизобить эту функцию участника, чтобы обеспечить глобальную обработку исключений. Позвоните в базовую функциональность только в том случае, если вы хотите, чтобы окно сообщений было отображено.

## <a name="cwinappregister"></a><a name="register"></a>CWinApp::Регистрация

Выполняет любые регистрационные `RegisterShellFileTypes`задачи, не обрабатываемые .

```
virtual BOOL Register();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Remarks

Реализация по умолчанию просто возвращает TRUE. Переопределить эту функцию, чтобы обеспечить любые индивидуальные шаги регистрации.

## <a name="cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>CWinApp:RegisterShellFileTypes

Вызовите эту функцию участника, чтобы зарегистрировать все типы документов вашего приложения с помощью менеджера файлов Windows.

```cpp
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>Параметры

*bКоммат*<br/>
(в) TRUE добавляет регистрационные записи для команд оболочки Print и Print To, позволяя пользователю печатать файлы непосредственно из оболочки или перетаскивая файл на объект принтера. Он также добавляет ключ DefaultIcon. По умолчанию этот параметр FALSE для обратной совместимости.

### <a name="remarks"></a>Remarks

Это позволяет пользователю открыть файл данных, созданный вашим приложением, дважды щелкая его из файла Manager. Звоните `RegisterShellFileTypes` после вызова [AddDocTemplate](#adddoctemplate) для каждого из шаблонов документов в приложении. Также позвоните в функцию участника `RegisterShellFileTypes` [EnableShellOpen](#enableshellopen) при вызове.

`RegisterShellFileTypes`итерирует через список объектов [CDocTemplate,](../../mfc/reference/cdoctemplate-class.md) которые приложение поддерживает, и для каждого шаблона документа добавляет записи в базу данных регистрации, которую Windows поддерживает для ассоциаций файлов. File Manager использует эти записи, чтобы открыть файл данных, когда пользователь дважды щелкает его. Это устраняет необходимость отправки . Файл REG с вашим заявлением.

> [!NOTE]
> `RegisterShellFileTypes`работает только в том случае, если пользователь запускает программу с правами администратора. Если программа не имеет прав администратора, она не может изменять ключи реестра.

Если база данных регистрации уже связывает данное расширение имени файла с другим типом файла, новая ассоциация не создается. Просмотрите `CDocTemplate` класс для формата строк, необходимых для регистрации этой информации.

## <a name="cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>CWinApp:RegisterWithRestartManager

Регистрирует приложение с менеджером перезагрузки.

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
|Параметр|Описание|
|*bRegisterВосстановлениеCallback*|(в) TRUE указывает, что в данном экземпляре приложения используется функция обратного вызова восстановления; FALSE указывает, что это не так. Фрейм вызывает функцию обратного вызова восстановления, когда приложение неожиданно выходит из него. Для получения дополнительной информации [см. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*strRestartИтификер*|(в) Уникальная строка, идентифицирует этот экземпляр менеджера перезагрузки. Идентификатор менеджера перезагрузки уникален для каждого экземпляра приложения.|
|*pwzCommandLineArgs*|(в) Строка, содержащая любые дополнительные аргументы из командной строки.|
|*dwRestartФлаги*|(в) Дополнительные флаги для менеджера перезагрузки. Дополнительные сведения см. в разделе «Примечания».|
|*pRecoveryCallback*|(в) Функция обратного вызова восстановления. Эта функция должна принимать параметр LPVOID в качестве ввода и возвращать DWORD. Функция обратного вызова `CWinApp::ApplicationRecoveryCallback`по умолчанию .|
|*lpvParam*|(в) Параметр ввода для функции возврата восстановления. Для получения дополнительной информации [см. CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|
|*dwPingInterval*|(в) Продолжительность времени, в течение которого менеджер перезагрузки ждет возврата функции возврата. Этот параметр находится в миллисекундах.|
|*dwCallbackФлаги*|(в) Флаги перешли к функции обратного вызова восстановления. Зарезервировано для последующего использования.|

### <a name="return-value"></a>Возвращаемое значение

S_OK, если метод удачен; в противном случае код ошибки.

### <a name="remarks"></a>Remarks

Если приложение использует реализацию MFC по умолчанию для автоматического `RegisterWithRestartManager`сохранения файлов, следует использовать простую версию. Используйте сложную `RegisterWithRestartManager` версию, если вы хотите настроить поведение автосохранения вашего приложения.

Если вы называете этот метод пустой строкой `RegisterWithRestartManager` для *strRestartIdentifier,* создается уникальная строка идентификатора для этого экземпляра менеджера перезагрузки.

Когда приложение неожиданно выходит из него, менеджер перезагрузки перезапускает приложение из командной строки и предоставляет уникальный идентификатор перезагрузки в качестве дополнительного аргумента. В этом сценарии `RegisterWithRestartManager` фреймворк вызываетдвась. Первый звонок исходит от [CWinApp::InitInstance](#initinstance) с пустой строкой для идентификатора строки. Затем, метод [CWinApp::ProcessShellCommand](#processshellcommand) звонки `RegisterWithRestartManager` с уникальным идентификатором перезагрузки.

После регистрации приложения у менеджера перезагрузки менеджер перезагрузки отслеживает приложение. Если приложение неожиданно выходит из системы, менеджер перезагрузки вызывает функцию обратного вызова восстановления во время процесса выключения. Менеджер перезагрузки ждет *dwPingInterval* ответа от функции обратного вызова восстановления. Если функция обратного вызова восстановления не отвечает в течение этого времени, приложение выходит без выполнения функции обратного вызова.

По умолчанию dwRestartFlags не поддерживаются, но предоставляются для использования в будущем. Возможные значения *dwRestartFlags* следующие:

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesatRestart

Определяет, возобновляет ли менеджер перезагрузки файлы, которые были открыты при неожиданном выходе приложения.

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки вновь открывает ранее открытые файлы; FALSE указывает, что менеджер перезагрузки этого не делает.

## <a name="cwinapprestartinstance"></a><a name="restartinstance"></a>CWinApp::RestartInstance

Обрабатывает перезагрузку приложения, инициированную менеджером перезагрузки.

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если обработчик восстановления данных открывает ранее открытые документы; FALSE, если обработчик восстановления данных имеет ошибку или если нет ранее открытых документов.

### <a name="remarks"></a>Remarks

Когда менеджер перезагрузки перезапускает приложение, фреймворк вызывает этот метод. Этот метод восстанавливает обработчик восстановления данных и восстанавливает автоматически сохраненные файлы. Этот метод вызывает [CDataRecoveryHandler::RestoreAutosavedDocuments,](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) чтобы определить, хочет ли пользователь восстановить автоматически сохраненные файлы.

Этот метод возвращает FALSE, если [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) определяет, что не было открытых документов. Если открытых документов не было, заявление начинается обычно.

## <a name="cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesatRestart

Определяет, восстанавливает ли менеджер перезагрузки автоматически сохраненные файлы при перезагрузке приложения.

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки восстанавливает автоматически сохраненные файлы; FALSE указывает, что менеджер перезагрузки этого не делает.

## <a name="cwinapprun"></a><a name="run"></a>CWinApp::Run

Обеспечивает цикл сообщения по умолчанию.

```
virtual int Run();
```

### <a name="return-value"></a>Возвращаемое значение

**Значение Int,** которое `WinMain`возвращается .

### <a name="remarks"></a>Remarks

`Run`приобретает и отправляет сообщения Windows до тех пор, пока приложение не получит WM_QUIT сообщения. Если очередь сообщений приложения в настоящее время не содержит сообщений, `Run` [звоните OnIdle](#onidle) для выполнения обработки простоя. Входящие сообщения переходят в функцию участника [PreTranslateMessage](#pretranslatemessage) для `TranslateMessage` специальной обработки, а затем в функцию Windows для стандартного перевода клавиатуры; наконец, `DispatchMessage` функция Windows называется.

`Run`редко переопределяется, но вы можете переопределить его, чтобы обеспечить особое поведение.

## <a name="cwinapprunautomated"></a><a name="runautomated"></a>CWinApp::RunAutomated

Вызовите эту функцию, чтобы определить, присутствует ли параметр **«/Автоматизация»** или **«Автоматизация»,** который указывает, было ли серверное приложение запущено клиентским приложением.

```
BOOL RunAutomated();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вариант был найден; в противном случае 0.

### <a name="remarks"></a>Remarks

При наличии параметр удаляется из командной строки. Для получения дополнительной информации об [Automation Servers](../../mfc/automation-servers.md)автоматизации OLE см.

## <a name="cwinapprunembedded"></a><a name="runembedded"></a>CWinApp::RunEmbedded

Вызовите эту функцию, чтобы определить, присутствует ли опция **"/Embedding"** или **"-Embedding**", что указывает на то, было ли серверное приложение запущено клиентским приложением.

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вариант был найден; в противном случае 0.

### <a name="remarks"></a>Remarks

При наличии параметр удаляется из командной строки. Для получения дополнительной информации о встраиваемии см. [Servers: Implementing a Server](../../mfc/servers-implementing-a-server.md)

## <a name="cwinappsaveallmodified"></a><a name="saveallmodified"></a>CWinApp:SaveAllModified

Вызывается в рамках, чтобы сохранить все документы, когда основное окно кадра приложения должно быть закрыто, или через WM_QUERYENDSESSION сообщение.

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если безопасно прекратить применение; 0, если не безопасно прекратить применение.

### <a name="remarks"></a>Remarks

Выполнение этой функции элемента по умолчанию вызывает [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) функция участника в свою очередь для всех измененных документов в приложении.

## <a name="cwinappselectprinter"></a><a name="selectprinter"></a>CWinApp::SelectPrinter

Вызовите эту функцию участника, чтобы выбрать определенный принтер и отпустите принтер, который был ранее выбран в поле Print Dialog.

```cpp
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>Параметры

*hDevNames*<br/>
Ручка для tructure [DEVNAMES,](/windows/win32/api/commdlg/ns-commdlg-devnames)которая идентифицирует имена драйверов, устройств и выходных портов конкретного принтера.

*hDevMode*<br/>
Ручка для структуры [DEVMODE,](/windows/win32/api/wingdi/ns-wingdi-devmodea) которая определяет информацию о инициализации устройства и среде принтера.

*bFreeOld*<br/>
Освобождает ранее выбранный принтер.

### <a name="remarks"></a>Remarks

Если *hDevMode* и *hDevNames* `SelectPrinter` являются NULL, использует текущий принтер по умолчанию.

## <a name="cwinappsethelpmode"></a><a name="sethelpmode"></a>CWinApp:SetHelpMode

Устанавливает тип справки приложения.

```cpp
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>Параметры

*eHelpType*<br/>
Определяет тип справки для использования. Смотрите [CWinApp::m_eHelpType](#m_ehelptype) для получения дополнительной информации.

### <a name="remarks"></a>Remarks

Устанавливает тип справки приложения.

Чтобы настроить тип справки приложения в HTMLHelp, вы можете позвонить [enableHTMLHelp.](#enablehtmlhelp) Как только `EnableHTMLHelp`вы звоните, ваше приложение должно использовать HTMLHelp в качестве своего приложения помощи. Если вы хотите изменить, чтобы использовать `SetHelpMode` WinHelp, вы `afxWinHelp`можете позвонить и установить *eHelpType.*

## <a name="cwinappsetregistrykey"></a><a name="setregistrykey"></a>CWinApp::SetRegistryKey

Вызывает настройки приложения, которые будут храниться в реестре вместо файлов INI.

```cpp
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>Параметры

*lpszRegistryKey*<br/>
Указатель на строку, содержащую имя ключа.

*nIDRegistryKey*<br/>
Идентификатор строки ресурса, содержащий имя ключа реестра.

### <a name="remarks"></a>Remarks

Эта функция устанавливает *m_pszRegistryKey,* который `GetProfileInt`затем `GetProfileString` `WriteProfileInt`используется, `WriteProfileString` , `CWinApp`и функции члена . Если эта функция была вызвана, список самых недавно используемых (MRU) файлов также хранится в реестре. Ключ реестра, как правило, название компании. Он хранится в ключе следующей формы: HKEY_CURRENT_USER'Software\\<название\> \\ \>\> \\ компании<название\> \\ приложения<название раздела<значение .

## <a name="cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>CWinApp::ПоддержкаВосстановления приложений

Определяет, восстанавливает ли менеджер перезагрузки приложение, которое неожиданно вышло.

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки восстанавливает приложение; FALSE указывает, что менеджер перезагрузки этого не делает.

## <a name="cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveatInterval

Определяет, автоматически ли менеджер перезагрузки сохраняет открытые документы с регулярным интервалом.

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки автоматически сохраняет открытые документы; FALSE указывает, что менеджер перезагрузки этого не делает.

## <a name="cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveatRestart

Определяет, автоматически ли менеджер перезагрузки сохраняет открытые документы при перезагрузке приложения.

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает на то, что менеджер перезагрузки автоматически сохраняет открытые документы при перезагрузке приложения; FALSE указывает, что менеджер перезагрузки этого не делает.

## <a name="cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager

Определяет, поддерживает ли приложение менеджер перезагрузки.

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE указывает, что приложение поддерживает менеджера перезагрузки; FALSE указывает, что приложение не делает.

## <a name="cwinappunregister"></a><a name="unregister"></a>CWinApp::Unregister

Отменить регистрацию всех файлов, зарегистрированных объектом приложения.

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.

### <a name="remarks"></a>Remarks

Функция `Unregister` отменяет регистрацию, выполняемую объектом приложения и функцией [Регистра.](#register) Как правило, обе функции неявно называются MFC и поэтому не отображаются в вашем коде.

Переопределить эту функцию для выполнения пользовательских шагов нерегистрации.

## <a name="cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes

Вызовите эту функцию участника, чтобы отменить регистрацию всех типов документов вашего приложения с помощью менеджера файлов Windows.

```cpp
void UnregisterShellFileTypes();
```

## <a name="cwinappwinhelp"></a><a name="winhelp"></a>CWinApp::WinHelp

Вызовите эту функцию участника, чтобы вызвать приложение WinHelp.

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>Параметры

*dwData*<br/>
Определяет дополнительные данные. Используемое значение зависит от значения параметра *nCmd.*

*nCmd*<br/>
Задает тип запрошенной справки. Список возможных значений и способы их влияния на параметр *dwData* можно узнать в функции [WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) Windows.

### <a name="remarks"></a>Remarks

Платформа также вызывает эту функцию для вызова приложения WinHelp.

Платформа автоматически закроет приложение WinHelp, когда ваше приложение будет прекращено.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

## <a name="cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>CWinApp::WriteProfileBinary

Позвоните этой функции участника, чтобы написать двоичные данные в указанный раздел реестра приложения или . Файл INI.

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись. Если раздел не существует, он создается. Название раздела является независимым случаем; строка может быть любой комбинацией верхних и нижних букв.

*lpszEntry*<br/>
Указывает на нулевую строку, содержащую запись, в которую должно быть написано значение. Если запись не существует в указанном разделе, она создается.

*Pdata*<br/>
Указывает на данные, которые должны быть написаны.

*nБайт*<br/>
Содержит количество байтов, которые должны быть написаны.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

Этот пример `CWinApp* pApp = AfxGetApp();` используется, чтобы получить в классе CWinApp иллюстрирующие способ, который `WriteProfileBinary` и `GetProfileBinary` может быть использован из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

Для другого примера см. пример [для CWinApp:GetProfileBinary](#getprofilebinary).

## <a name="cwinappwriteprofileint"></a><a name="writeprofileint"></a>CWinApp::WriteProfileInt

Позвоните в эту функцию участника, чтобы записать указанное значение в указанный раздел реестра приложения или . Файл INI.

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись. Если раздел не существует, он создается. Название раздела является независимым случаем; строка может быть любой комбинацией верхних и нижних букв.

*lpszEntry*<br/>
Указывает на нулевую строку, содержащую запись, в которую должно быть написано значение. Если запись не существует в указанном разделе, она создается.

*nValue*<br/>
Содержит значение, подносиве себя авторизовать.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

Этот пример `CWinApp* pApp = AfxGetApp();` использует, чтобы получить на класс CWinApp иллюстрирующие `WriteProfileString`способ, `WriteProfileInt`что , `GetProfileString`и `GetProfileInt` может быть использован из любой функции в приложении MFC.

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Для другого примера см. пример [для CWinApp:GetProfileInt](#getprofileint).

## <a name="cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>CWinApp::WriteProfileString

Вызовите эту функцию участника, чтобы написать указанную строку в указанный раздел реестра приложения или . Файл INI.

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Параметры

*lpszSection*<br/>
Указывает на строку с нулевым завершением, которая определяет раздел, содержащий запись. Если раздел не существует, он создается. Название раздела является независимым случаем; строка может быть любой комбинацией верхних и нижних букв.

*lpszEntry*<br/>
Указывает на нулевую строку, содержащую запись, в которую должно быть написано значение. Если запись не существует в указанном разделе, она создается. Если этот параметр NULL, раздел, указанный *lpszSection,* удаляется.

*lpszValue*<br/>
Указывает на строку, которая должна быть написана. Если этот параметр NULL, вход, указанный параметром *lpszEntry,* удаляется.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

Для другого примера см. пример [для CWinApp:GetProfileInt](#getprofileint).

## <a name="cwinappsetappid"></a><a name="setappid"></a>CWinApp::SetAppID

Явно устанавливает идентификатор модели пользователя приложения для приложения. Этот метод следует назвать до того, как пользовательский интерфейс будет представлен пользователю (лучшее место - конструктор приложения).

```cpp
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>Параметры

*lpcszAppID*<br/>
Определяет идентификатор модели пользователя приложения.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[Класс CWinThread](../../mfc/reference/cwinthread-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Практическое руководство. Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)
