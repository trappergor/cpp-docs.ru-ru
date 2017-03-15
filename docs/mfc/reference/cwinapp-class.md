---
title: "CWinApp-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinApp
- hInstance
dev_langs:
- C++
helpviewer_keywords:
- CWinApp class
- application objects [C++]
- HINSTANCE
- main object
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 292816c8f753a7b47b563a3fcd0fa336e08acd6a
ms.lasthandoff: 02/24/2017

---
# <a name="cwinapp-class"></a>CWinApp-класс
Базовый класс, от которого необходимо наследовать объект приложения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CWinApp : public CWinThread  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinApp::CWinApp](#cwinapp)|Создает объект `CWinApp`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinApp::AddDocTemplate](#adddoctemplate)|Добавляет список приложений шаблонов документов доступны шаблон документа.|  
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|Добавляет имя файла в списке недавно использованных файлов (MRU).|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|Вызывается платформой, когда приложение неожиданно завершает работу.|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|Закрывает все открытые документы.|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|Создает контекст устройства принтера.|  
|[CWinApp::DelRegTree](#delregtree)|Удаляет указанный ключ и всем его подразделам.|  
|[CWinApp::DoMessageBox](#domessagebox)|Реализует [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для приложения.|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|Включение и отключение, включение курсор ожидания.|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|Позволяет приложению `D2D` поддержки. Данный метод следует вызывать до инициализации основного окна.|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|Реализует HTMLHelp для приложения, а не WinHelp.|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|Разрешает взаимодействие с панели задач.|  
|[CWinApp::ExitInstance](#exitinstance)|Переопределение для очистки, когда приложение завершает работу.|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|Получает входной параметр для метода восстановления приложений.|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|Возвращает время ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата.|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|Возвращает флаги диспетчера перезапуска.|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\ProfileName «Программное обеспечение».|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|Возвращает обработчик восстановления данных для этого экземпляра приложения.|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|Возвращает позицию первого шаблона документа.|  
|[CWinApp::GetHelpMode](#gethelpmode)|Получает тип справки, используемые приложением.|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|Получает положение шаблон документа. Можно использовать рекурсивно.|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|Извлекает устройства по умолчанию.|  
|[CWinApp::GetProfileBinary](#getprofilebinary)|Получает двоичные данные из записи в приложении. INI-файл.|  
|[CWinApp::GetProfileInt](#getprofileint)|Возвращает целое из записи в приложении. INI-файл.|  
|[CWinApp::GetProfileString](#getprofilestring)|Извлекает строки из записи в приложении. INI-файл.|  
|[CWinApp::GetSectionKey](#getsectionkey)|Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection «Программное обеспечение».|  
|[CWinApp::HideApplication](#hideapplication)|Скрывает приложения перед закрытием всех документов.|  
|[CWinApp::HtmlHelp](#htmlhelp)|Вызовы `HTMLHelp` функции Windows.|  
|[CWinApp::InitInstance](#initinstance)|Переопределение для выполнения инициализации экземпляра Windows, таких как создание объектов-окон.|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Указывает, включена ли взаимодействия с панелью задач Windows 7.|  
|[CWinApp::LoadCursor](#loadcursor)|Загружает ресурс курсора.|  
|[CWinApp::LoadIcon](#loadicon)|Загружает ресурс значка.|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|Предварительно загружает Windows OEM курсора, **OCR_** указать константы в WINDOWS. З.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Загружает предопределенный значком Windows OEM, **OIC_** указать константы в WINDOWS. З.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|Загружает Windows предопределенные курсора, **IDC_** указать константы в WINDOWS. З.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Загружает предварительно определенных значок Windows, **IDI_** указать константы в WINDOWS. З.|  
|[CWinApp::OnDDECommand](#onddecommand)|Вызывается платформой динамических данных exchange (DDE) выполните команду.|  
|[CWinApp::OnIdle](#onidle)|Переопределение, чтобы выполнить обработку времени простоя для конкретного приложения.|  
|[CWinApp::OpenDocumentFile](#opendocumentfile)|Вызывается платформой для открытия документа из файла.|  
|[CWinApp::ParseCommandLine](#parsecommandline)|Выполняет синтаксический анализ отдельных параметров и флаги в командной строке.|  
|[CWinApp::PreTranslateMessage](#pretranslatemessage)|Фильтры сообщений перед их отправкой в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|Перехватывает определенных сообщений, прежде чем они достигнут приложения.|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|Обрабатывает аргументы командной строки и флаги.|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|Перехватывает все необработанные исключения, создаваемые сообщения приложения и обработчиков команд.|  
|[CWinApp::Register](#register)|Выполняет настраиваемые регистрацию.|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|Регистрирует приложение с диспетчером перезапуска.|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|Определяет, открывается ли файлы, которые были открыты, когда приложение неожиданно завершили работу, диспетчер перезапуска.|  
|[CWinApp::RestartInstance](#restartinstance)|Обрабатывает инициировано диспетчера перезапуска перезапуск приложения.|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|Определяет, восстанавливает ли диспетчер перезапуска автоматически сохраненная файлов после его перезапуска приложения.|  
|[CWinApp::Run](#run)|Запускает цикл обработки сообщений по умолчанию. Переопределения, чтобы настроить цикл обработки сообщений.|  
|[CWinApp::RunAutomated](#runautomated)|Тесты командной строки приложения для **/Automation** параметр. Является устаревшей. Вместо этого используйте значение в [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated) после вызова метода [ParseCommandLine](#parsecommandline).|  
|[CWinApp::RunEmbedded](#runembedded)|Тесты командной строки приложения для **и внедрение** параметр. Является устаревшей. Вместо этого используйте значение в [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded) после вызова метода [ParseCommandLine](#parsecommandline).|  
|[CWinApp::SaveAllModified](#saveallmodified)|Пользователю будет предложено сохранить все измененные документы.|  
|[CWinApp::SelectPrinter](#selectprinter)|Выбор принтера, определено пользователем через диалоговое окно печати.|  
|[CWinApp::SetHelpMode](#sethelpmode)|Задает и инициализирует тип справки, используемые приложением.|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|Определяет, восстанавливает ли диспетчер перезапуска приложения, неожиданно завершили работу.|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|Определяет ли преждевременном диспетчера перезапуска открывать документы с определенным интервалом.|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|Определяет, является ли преждевременном диспетчера перезапуска открытые документы после перезапуска приложения.|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|Определяет, поддерживает ли приложение диспетчера перезапуска.|  
|[CWinApp::Unregister](#unregister)|Отменяет все известные зарегистрированы по `CWinApp` объекта.|  
|[CWinApp::WinHelp](#winhelp)|Вызовы `WinHelp` функции Windows.|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|Записывает двоичные данные для записи в приложении. INI-файл.|  
|[CWinApp::WriteProfileInt](#writeprofileint)|Записывает целое число для записи в приложении. INI-файл.|  
|[CWinApp::WriteProfileString](#writeprofilestring)|Записывает строку в запись в приложении. INI-файл.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|Позволяет пользователю открывать файлы данных в диспетчере файлов Windows.|  
|[CWinApp::LoadStdProfileSettings](#loadstdprofilesettings)|Загружает standard. Параметры INI-файла и позволяет наиболее часто Используемых файлов функции списка.|  
|[CWinApp::OnContextHelp](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 справки в приложении.|  
|[CWinApp::OnFileNew](#onfilenew)|Реализует `ID_FILE_NEW` команды.|  
|[CWinApp::OnFileOpen](#onfileopen)|Реализует `ID_FILE_OPEN` команды.|  
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|Реализует `ID_FILE_PRINT_SETUP` команды.|  
|[CWinApp::OnHelp](#onhelp)|Обрабатывает справку F1 в приложении (с использованием текущего контекста).|  
|[CWinApp::OnHelpFinder](#onhelpfinder)|Обрабатывает команды `ID_HELP_FINDER` и `ID_DEFAULT_HELP`.|  
|[CWinApp::OnHelpIndex](#onhelpindex)|Обрабатывает команду `ID_HELP_INDEX` и предоставляет раздел справки по умолчанию.|  
|[CWinApp::OnHelpUsing](#onhelpusing)|Обрабатывает команду `ID_HELP_USING`.|  
|[CWinApp::RegisterShellFileTypes](#registershellfiletypes)|Регистрирует типы документов приложения с помощью диспетчера файлов Windows.|  
|[CWinApp::SetAppID](#setappid)|Явно задает идентификатор модели приложения пользователя для приложения. Этот метод должен вызываться перед любой пользовательский интерфейс предоставляется пользователю (лучше всего — конструктор приложений).|  
|[CWinApp::SetRegistryKey](#setregistrykey)|Параметры приложения сохраняются в реестре, а не в результате. INI-файлы.|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|Отменяет регистрацию типов документов приложения с помощью диспетчера файлов Windows.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|Указывает, является ли пользователь режим контекста справки (обычно вызывается с помощью клавиши SHIFT + F1).|  
|[CWinApp::m_eHelpType](#m_ehelptype)|Указывает тип справки, используемые приложением.|  
|[CWinApp::m_hInstance](#m_hinstance)|Определяет текущий экземпляр приложения.|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|Точки нулем строку, которая задает командную строку для приложения.|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|Указывает, как будет первоначально отображаться окно.|  
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|Указатель на главное окно приложения-контейнера, когда сервер OLE является активным на месте.|  
|[CWinApp::m_pszAppID](#m_pszappid)|Идентификатор приложения пользователя модели.|  
|[CWinApp::m_pszAppName](#m_pszappname)|Задает имя приложения.|  
|[CWinApp::m_pszExeName](#m_pszexename)|Имя модуля приложения.|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|Путь к файлу справки приложения.|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|Приложения. Имя INI-файла.|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|Используется для определения полного реестра для хранения параметров профиля приложения.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|Флаги, которые определяют поведение диспетчера перезапуска.|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|Продолжительность времени в миллисекундах между преждевременном.|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|Указатель на обработчик восстановления данных для приложения.|  
  
## <a name="remarks"></a>Примечания  
 Объект приложения предоставляет функции-члены для инициализации приложения (и каждого экземпляра), а также для запуска приложения.  
  
 Каждого приложения, использующего Microsoft Foundation classes может содержать только один объект, производный от `CWinApp`. Этот объект создается при создании других глобальных объектов C++ и уже доступна, когда Windows вызывает `WinMain` функции, которая является результатом библиотеки Microsoft Foundation Class. Объявите производный `CWinApp` объекта на глобальном уровне.  
  
 При наследовании класса приложения из `CWinApp`, переопределить [InitInstance](#initinstance) функции-члена для создания объекта главного окна приложения.  
  
 В дополнение к `CWinApp` функции-члены библиотеки классов Microsoft Foundation предоставляет следующие глобальные функции для доступа к вашей `CWinApp` объекта и другие глобальные сведения:  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp) получает указатель на `CWinApp` объект.  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle) Получает дескриптор текущего экземпляра приложения.  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle) Получает дескриптор для ресурсов приложения.  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname) получает указатель на строку, содержащую имя приложения. Кроме того Если имеется указатель на `CWinApp` , используйте `m_pszExeName` для получения имени приложения.  
  
 В разделе [CWinApp: класс приложения](../../mfc/cwinapp-the-application-class.md) для получения дополнительных сведений о `CWinApp` класса, включая обзор следующие:  
  
- `CWinApp`-Производный код, написанный с помощью мастера приложений.  
  
- `CWinApp`в роли в последовательность выполнения приложения.  
  
- `CWinApp`в реализациях функции-члена по умолчанию.  
  
- `CWinApp`его ключ переопределяемости.  
  
 **M_hPrevInstance** член данных больше не существует. Сведения об определении предыдущего экземпляра `CWinApp`, см. в статье базы знаний «Идентификации предыдущего экземпляра из приложения» (KB106385) в [http://support.microsoft.com/default.aspxscid=kb;en-us;106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="a-nameadddoctemplatea--cwinappadddoctemplate"></a><a name="adddoctemplate"></a>CWinApp::AddDocTemplate  
 Вызовите эту функцию-член для добавления в список шаблонов доступных документов, приложение сохраняет шаблон документа.  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 `pTemplate`  
 Указатель на `CDocTemplate` для добавления.  
  
### <a name="remarks"></a>Примечания  
 Следует добавить шаблоны в приложение всех документов перед вызовом метода [RegisterShellFileTypes](#registershellfiletypes).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#35;](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="a-nameaddtorecentfilelista--cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>CWinApp::AddToRecentFileList  
 Вызов этой функции-члена для добавления `lpszPathName` в список последних Использованных файлов.  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPathName`  
 Путь к файлу.  
  
### <a name="remarks"></a>Примечания  
 Следует вызвать [LoadStdProfileSettings](#loadstdprofilesettings) функции-члена для загрузки текущий список файлов, прежде чем использовать эту функцию-член.  
  
 Платформа вызывает эту функцию-член, когда он открывает файл, или выполняет команду Сохранить как, чтобы сохранить файл с новым именем.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#36;](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="a-nameapplicationrecoverycallbacka--cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>CWinApp::ApplicationRecoveryCallback  
 Вызывается платформой, когда приложение неожиданно завершает работу.  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpvParam`  
 Зарезервировано для будущего использования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 0, если этот метод выполнен успешно; ненулевое значение, если произошла ошибка.  
  
### <a name="remarks"></a>Примечания  
 Если приложение поддерживает диспетчер перезапуска, платформа вызывает эту функцию, когда приложение неожиданно завершает работу.  
  
 Реализация по умолчанию `ApplicationRecoveryCallback` использует `CDataRecoveryHandler` для сохранения списка открытых документов в реестре. Этот метод не сохранять не все файлы.  
  
 Для настройки поведения, переопределяют эту функцию в производном [класс CWinApp](../../mfc/reference/cwinapp-class.md) или передайте собственный метод восстановления приложения в качестве параметра [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
##  <a name="a-nameclosealldocumentsa--cwinappclosealldocuments"></a><a name="closealldocuments"></a>CWinApp::CloseAllDocuments  
 Вызовите эту функцию-член, чтобы закрыть все открытые документы перед выходом.  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>Параметры  
 `bEndSession`  
 Указывает, является ли к завершению сеанса Windows. Это **TRUE** Если сеанс завершается; в противном случае **FALSE**.  
  
### <a name="remarks"></a>Примечания  
 Вызов [HideApplication](#hideapplication) перед вызовом метода `CloseAllDocuments`.  
  
##  <a name="a-namecreateprinterdca--cwinappcreateprinterdc"></a><a name="createprinterdc"></a>CWinApp::CreatePrinterDC  
 Вызовите эту функцию-член для создания контекста устройства (DC) принтера из выбранного принтера.  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>Параметры  
 `dc`  
 Ссылка на контекст устройства принтера.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если контекст устройства принтера создана успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 `CreatePrinterDC`Инициализирует контекст устройства, переданное по ссылке, чтобы можно было использовать для печати.  
  
 Если функция выполнена успешно, после завершения печати, должны уничтожить контекст устройства. Можно позволить деструктор [CDC](../../mfc/reference/cdc-class.md) сделать объект или выполнять его явным образом путем вызова [CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc).  
  
##  <a name="a-namecwinappa--cwinappcwinapp"></a><a name="cwinapp"></a>CWinApp::CWinApp  
 Создает `CWinApp` объекта и передает `lpszAppName` сохраняется как имя приложения.  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszAppName`  
 Завершающим нулем строка, содержащая имя приложения, использующего Windows. Если этот аргумент не указан или является **NULL**, `CWinApp` использует строки ресурсов **AFX_IDS_APP_TITLE** или имя исполняемого файла.  
  
### <a name="remarks"></a>Примечания  
 Необходимо создать один глобальный объект вашего `CWinApp`-производного класса. Можно иметь только одну `CWinApp` объект в приложении. Конструктор сохраняет указатель на `CWinApp` объекта, чтобы `WinMain` можно вызвать объект функции-члены для инициализации и запуска приложения.  
  
##  <a name="a-namedelregtreea--cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::DelRegTree  
 Удаление определенного раздела реестра и его подразделов.  
  
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
 *hParentKey*  
 Дескриптор раздела реестра.  
  
 *strKeyName*  
 Имя удаляемого раздела реестра.  
  
 *pTM*  
 Указатель на объект catltransactionmanager..  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение равно ERROR_SUCCESS. Если функция завершается с ошибкой, возвращается код ненулевое значение ошибки, определенные в файле Winerror.h.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для удаления указанного ключа и его подразделов.  
  
##  <a name="a-namedomessageboxa--cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::DoMessageBox  
 Платформа вызывает эту функцию-член для реализации окно сообщения для глобальной функции [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox).  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPrompt*  
 Адрес текст в окне сообщения.  
  
 `nType`  
 В окне сообщения [стиля](../../mfc/reference/message-box-styles.md).  
  
 `nIDPrompt`  
 Индекс строки контекста справки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает те же значения, что `AfxMessageBox`.  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член для окна сообщения; Используйте `AfxMessageBox` вместо.  
  
 Переопределить эту функцию-член для настройки на уровне приложения обработки `AfxMessageBox` вызовов.  
  
##  <a name="a-namedowaitcursora--cwinappdowaitcursor"></a><a name="dowaitcursor"></a>CWinApp::DoWaitCursor  
 Эта функция-член вызывается платформой для реализации [CWaitCursor](../../mfc/reference/cwaitcursor-class.md), [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor), и [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>Параметры  
 `nCode`  
 Если этот параметр равен 1, появится курсор ожидания. Если значение равно 0, курсор ожидания восстанавливается без приращения счетчика ссылок. Если значение –&1;, курсор ожидания будет завершен.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию реализует курсор с песочными часами. `DoWaitCursor`поддерживает счетчик ссылок. Когда положительно, отображается курсор с песочными часами.  
  
 Хотя обычно не вызывается `DoWaitCursor` напрямую, можно переопределить эту функцию-член для изменения курсор ожидания или выполнять дополнительную обработку при отображении курсор ожидания.  
  
 Более простой способ, более простой способ реализации курсор ожидания, используйте `CWaitCursor`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#37;](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="a-nameenabled2dsupporta--cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 Включает поддержку приложением D2D. Данный метод следует вызывать до инициализации основного окна.  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>Параметры  
 `d2dFactoryType`  
 Потоковая модель фабрики D2D и ресурсы, которые он создает.  
  
 `writeFactoryType`  
 Значение, указывающее, будет ли объект фабрики записи совместно или изолированной  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если поддержка D2D была включена, FALSE — в противном случае  
  
##  <a name="a-nameenablehtmlhelpa--cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>CWinApp::EnableHtmlHelp  
 Вызовите эту функцию-член из конструктора вашей `CWinApp`-производный класс для использования HTMLHelp справки в приложении.  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameenableshellopena--cwinappenableshellopen"></a><a name="enableshellopen"></a>CWinApp::EnableShellOpen  
 Вызов этой функции обычно из вашего `InitInstance` переопределение, чтобы разрешить пользователям открывать файлы данных после двойного щелчка в диспетчер файлов файлы из вашего приложения.  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Примечания  
 Вызов `RegisterShellFileTypes` член работать совместно с функцией или предоставить. REG-файл в приложении для ручной регистрации типов документов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#38;](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="a-nameenabletaskbarinteractiona--cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp::EnableTaskbarInteraction  
 Разрешает взаимодействие с панели задач.  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, включены ли взаимодействия с панелью задач Windows 7 ( `TRUE`), или отключена ( `FALSE`).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` взаимодействия задач может быть включена или отключена.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться до создания главного окна, в противном случае он утверждает и возвращает `FALSE`.  
  
##  <a name="a-nameexitinstancea--cwinappexitinstance"></a><a name="exitinstance"></a>CWinApp::ExitInstance  
 Вызывается платформой из **запуска** функции-члена для выхода из этого экземпляра приложения.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код выхода приложения; 0 указывает без ошибок, а значения больше 0 указывает на ошибку. Это значение используется как возвращаемое значение `WinMain`.  
  
### <a name="remarks"></a>Примечания  
 Не вызывайте эту функцию-член из любого места но в **запуска** функции-члена.  
  
 Реализация по умолчанию эта функция записывает параметры framework в приложение. INI-файл. Переопределите эту функцию для очистки, когда приложение завершает работу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#39;](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="a-namegetapplicationrecoveryparametera--cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>CWinApp::GetApplicationRecoveryParameter  
 Получает входной параметр для метода восстановления приложений.  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Входной параметр по умолчанию для метода восстановления приложений.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция возвращает `NULL`.  
  
 Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
##  <a name="a-namegetapplicationrecoverypingintervala--cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>CWinApp::GetApplicationRecoveryPingInterval  
 Возвращает время ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата.  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Продолжительность времени в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Когда приложение регистрируется неожиданно завершает работу диспетчера перезапуска, приложение пытается сохранить открытые документы и вызывает функцию обратного вызова для восстановления. Функция обратного вызова для восстановления по умолчанию является [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).  
  
 Интервал времени, платформа ожидает функция обратного вызова для возврата восстановления — интервал проверки связи. Можно настроить интервал проверки связи, переопределив `CWinApp::GetApplicationRecoveryPingInterval` или предоставив пользовательское значение для `RegisterWithRestartManager`.  
  
##  <a name="a-namegetapplicationrestartflagsa--cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>CWinApp::GetApplicationRestartFlags  
 Возвращает флаги диспетчера перезапуска.  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Флаги для диспетчера перезапуска. Реализация по умолчанию возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 Флаги для диспетчера перезапуска не оказывают влияния реализацией по умолчанию. Они предназначены для использования в будущем.  
  
 Установить флаги при регистрации приложения с диспетчером перезапуска с помощью [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager).  
  
 Ниже приведены возможные значения для флагов диспетчер перезапуска.  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="a-namegetappregistrykeya--cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>CWinApp::GetAppRegistryKey  
 Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\ProfileName «Программное обеспечение».  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ключ приложения, если функция выполнена успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namegetdatarecoveryhandlera--cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>CWinApp::GetDataRecoveryHandler  
 Возвращает обработчик восстановления данных для этого экземпляра приложения.  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Обработчик восстановления данных для этого экземпляра приложения.  
  
### <a name="remarks"></a>Примечания  
 Каждого приложения, использующего диспетчер перезапуска должен иметь один экземпляр [CDataRecoveryHandler класса](../../mfc/reference/cdatarecoveryhandler-class.md). Этот класс отвечает за мониторинг открытые документы и файлы автосохранения. Поведение `CDataRecoveryHandler` зависит от конфигурации диспетчера перезапуска. Дополнительные сведения см. в разделе [CDataRecoveryHandler класса](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
 Этот метод возвращает `NULL` в операционных системах более ранних, чем [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Диспетчер перезапуска не поддерживается в операционных системах более ранних, чем [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 Если приложение не имеет обработчика восстановления данных в настоящее время, этот метод создает один и возвращает указатель на него.  
  
##  <a name="a-namegetfirstdoctemplatepositiona--cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>CWinApp::GetFirstDocTemplatePosition  
 Возвращает позицию первого шаблона документа в приложении.  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **ПОЗИЦИИ** значение, которое может использоваться для итерации или получения указатель объекта; **NULL** Если список пуст.  
  
### <a name="remarks"></a>Примечания  
 Используйте **ПОЗИЦИИ** значение, возвращаемое при обращении к [GetNextDocTemplate](#getnextdoctemplate) для получения первого [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объекта.  
  
##  <a name="a-namegethelpmodea--cwinappgethelpmode"></a><a name="gethelpmode"></a>CWinApp::GetHelpMode  
 Получает тип справки, используемые приложением.  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип справки, используемые приложением. В разделе [CWinApp::m_eHelpType](#m_ehelptype) для получения дополнительной информации.  
  
##  <a name="a-namegetnextdoctemplatea--cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>CWinApp::GetNextDocTemplate  
 Возвращает шаблон документа, идентифицируемый `pos`, затем устанавливает `pos` для **ПОЗИЦИИ** значение.  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим вызовом `GetNextDocTemplate` или [GetFirstDocTemplatePosition](#getfirstdoctemplateposition). Значение обновляется до следующей позиции при вызове этого метода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Можно использовать `GetNextDocTemplate` в прямой итерации цикла, если установить начальное положение, с помощью вызова `GetFirstDocTemplatePosition`.  
  
 Необходимо убедиться, что ваш **ПОЗИЦИИ** имеет допустимое значение. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.  
  
 Если шаблон полученного документа является последней доступной, затем новое значение `pos` имеет значение **NULL**.  
  
##  <a name="a-namegetprinterdevicedefaultsa--cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>CWinApp::GetPrinterDeviceDefaults  
 Вызовите эту функцию-член для подготовки принтер контекста устройства для печати.  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>Параметры  
 *pPrintDlg*  
 Указатель на [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Получает текущий по умолчанию из Windows. INI-файл как необходимые или использует последнюю конфигурацию принтера задано пользователем в параметры печати.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#40;](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]  
  
##  <a name="a-namegetprofilebinarya--cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>CWinApp::GetProfileBinary  
 Вызовите эту функцию-член для получения двоичных данных из записи в указанный раздел реестра приложения или. INI-файл.  
  
```  
BOOL GetProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSection*  
 Указывает нулем строка, указывающая раздела, содержащего запись.  
  
 *lpszEntry*  
 Точки нулем строку, которая содержит элемент, значение которого требуется получить.  
  
 *ppData*  
 Указатель на указатель, который будет получать адрес данных.  
  
 *pBytes*  
 Указывает UINT, который получит размер данных (в байтах).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член не должен учитываться регистр, поэтому строки в *lpszSection* и *lpszEntry* параметры могут различаться в случае.  
  
> [!NOTE]
> **GetProfileBinary** выделяет буфер и возвращается его адрес в \* *ppData*. Вызывающий объект отвечает за освобождение буфера с помощью **delete []**.  
  
> [!IMPORTANT]
>  Данные, возвращаемые этой функцией не обязательно NULL завершен и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#41;](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 Дополнительный пример в разделе [CWinApp::WriteProfileBinary](#writeprofilebinary).  
  
##  <a name="a-namegetprofileinta--cwinappgetprofileint"></a><a name="getprofileint"></a>CWinApp::GetProfileInt  
 Вызовите эту функцию-член для получения значения целого числа из записи в указанный раздел реестра приложения или. INI-файл.  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Указывает нулем строка, указывающая раздела, содержащего запись.  
  
 `lpszEntry`  
 Точки нулем строку, которая содержит элемент, значение которого требуется получить.  
  
 `nDefault`  
 Задает значение по умолчанию для возврата, если платформа не найдена запись.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целочисленное значение строки, которая предшествует указанную запись, если функция выполнена успешно. Возвращаемое значение является значением `nDefault` параметр, если функции не удается найти запись. Возвращаемое значение равно 0, если значение, соответствующее в указанный элемент не является целым числом.  
  
 Эта функция-член поддерживает значение в шестнадцатеричном формате. INI-файл. При извлечении целого числа со знаком, следует привести значение в `int`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член не должен учитываться регистр, поэтому строки в `lpszSection` и `lpszEntry` параметры могут различаться в случае.  
  
> [!IMPORTANT]
>  Данные, возвращаемые этой функцией не обязательно NULL завершен и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#42;](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 Дополнительный пример в разделе [CWinApp::WriteProfileInt](#writeprofileint).  
  
##  <a name="a-namegetprofilestringa--cwinappgetprofilestring"></a><a name="getprofilestring"></a>CWinApp::GetProfileString  
 Вызов этой функции-члена для извлечения строки, связанной с записью в указанный раздел реестра приложения или. INI-файл.  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Указывает нулем строка, указывающая раздела, содержащего запись.  
  
 `lpszEntry`  
 Точки нулем строку, которая содержит запись является строка которого требуется получить. Это значение не должно быть **NULL**.  
  
 `lpszDefault`  
 Указывает строковое значение по умолчанию для определенной записи, если не удается найти запись в файле настройки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращаемое значение является строкой в приложении. INI-файл или `lpszDefault` Если строка не найдена. Максимальная длина строки поддерживается платформой является `_MAX_PATH`. Если `lpszDefault` — **NULL**, возвращается пустая строка.  
  
### <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
>  Данные, возвращаемые этой функцией не обязательно NULL завершен и вызывающий объект должен выполнить проверку. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Другой пример, см. пример для [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namegetsectionkeya--cwinappgetsectionkey"></a><a name="getsectionkey"></a>CWinApp::GetSectionKey  
 Возвращает ключ для HKEY_CURRENT_USER\\\RegistryKey\AppName\lpszSection «Программное обеспечение».  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Имя ключа должны быть получены.  
  
 `pTM`  
 Указатель на `CAtlTransactionManager` объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ключ раздела, если функция выполнена успешно; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-namehideapplicationa--cwinapphideapplication"></a><a name="hideapplication"></a>CWinApp::HideApplication  
 Вызовите эту функцию-член для скрытия приложения перед закрытием открытых документов.  
  
```  
void HideApplication();
```  
  
##  <a name="a-namehtmlhelpa--cwinapphtmlhelp"></a><a name="htmlhelp"></a>CWinApp::HtmlHelp  
 Вызов этой функции-члена для вызова приложения HTMLHelp.  
  
```  
virtual void HtmlHelp(
    DWORD_PTR dwData,  
    UINT nCmd = 0x000F);
```  
  
### <a name="parameters"></a>Параметры  
 `dwData`  
 Задает дополнительные данные. Значение, которое используется зависит от значения `nCmd` параметр.  
  
 `nCmd`  
 Задает тип запрошенной справки. Список возможных значений и их влияние на `dwData` параметра, в разделе `uCommand` параметров, описанных в о HTMLHelp функции API в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Платформа также вызывает эту функцию для вызова приложения HTMLHelp.  
  
 Платформа автоматически закроет HTMLHelp приложения, когда приложение завершает работу.  
  
##  <a name="a-nameinitinstancea--cwinappinitinstance"></a><a name="initinstance"></a>CWinApp::InitInstance  
 Windows позволяет несколько копий одной и той же программы для запуска в то же время.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Концептуально инициализации приложения состоит из двух разделов: инициализации одноразовый приложения, что выполняется первый запуске программы и инициализацию экземпляра, который выполняется каждый раз копии запусков программы, включая в первый раз. Платформа framework реализация `WinMain` вызывает эту функцию.  
  
 Переопределение `InitInstance` для инициализации каждого нового экземпляра приложения, выполняющиеся в операционной системе Windows. Как правило, необходимо переопределить `InitInstance` для создания объекта главного окна и установки `CWinThread::m_pMainWnd` элемент данных для указания этого окна. Дополнительные сведения о переопределении функции-члена в разделе [CWinApp: класс приложения](../../mfc/cwinapp-the-application-class.md).  
  
> [!NOTE]
>  Приложения MFC необходимо инициализировать в виде однопотокового подразделения (STA). При вызове метода [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) в ваш `InitInstance` переопределения, укажите `COINIT_APARTMENTTHREADED` (а не `COINIT_MULTITHREADED`). Дополнительные сведения см. в разделе PRB: приложение MFC перестает отвечать при инициализации приложения в качестве многопоточного подразделения (828643) в [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCListView №&9;](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="a-nameistaskbarinteractionenableda--cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::IsTaskbarInteractionEnabled  
 Указывает, включена ли взаимодействия с панелью задач Windows 7.  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `TRUE` Если `EnableTaskbarInteraction` был вызван и операционной системы Windows 7 или более поздней версии.  
  
### <a name="remarks"></a>Примечания  
 Взаимодействие задач означает, что приложение MDI откроется содержимое дочерние формы MDI в отдельные эскизы на вкладках, которые появляются, если указатель мыши находится на кнопке панели задач приложения.  
  
##  <a name="a-nameloadcursora--cwinapploadcursor"></a><a name="loadcursor"></a>CWinApp::LoadCursor  
 Загружает ресурс курсора, названный `lpszResourceName` или заданные `nIDResource` из текущего исполняемого файла.  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  ```  
  
### Parameters  
 `lpszResourceName`  
 Points to a null-terminated string that contains the name of the cursor resource. You can use a `CString` for this argument.  
  
 `nIDResource`  
 ID of the cursor resource. For a list of resources, see [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Return Value  
 A handle to a cursor if successful; otherwise **NULL**.  
  
### Remarks  
 `LoadCursor` loads the cursor into memory only if it has not been previously loaded; otherwise, it retrieves a handle of the existing resource.  
  
 Use the [LoadStandardCursor](#loadstandardcursor) or [LoadOEMCursor](#loadoemcursor) member function to access the predefined Windows cursors.  
  
### Example  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 Loads the icon resource named by `lpszResourceName` or specified by `nIDResource` from the executable file.  
  
```  
LoadIcon(LPCTSTR lpszResourceName) HICON константу;  LoadIcon(UINT nIDResource) HICON константу;  ```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Указывает нулем строка, содержащая имя ресурса значка. Можно также использовать `CString` для этого аргумента.  
  
 `nIDResource`  
 Идентификатор ресурса значка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 `LoadIcon`загружает значок только в том случае, если она не была загружена ранее; в противном случае — возвращает дескриптор существующего ресурса.  
  
 Можно использовать [LoadStandardIcon](#loadstandardicon) или [LoadOEMIcon](#loadoemicon) функции-члена для доступа к предварительно определенных значков Windows.  
  
> [!NOTE]
>  Эта функция-член вызывается функция Win32 API [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072), который может загружать только значок, размер которого соответствует **SM_CXICON** и **SM_CYICON** значения метрик системы.  
  
##  <a name="a-nameloadoemcursora--cwinapploadoemcursor"></a><a name="loadoemcursor"></a>CWinApp::LoadOEMCursor  
 Загружает Windows предопределенные курсора ресурс, заданный параметром `nIDCursor`.  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDCursor`  
 **OCR_** манифеста идентификатор константы, указывающее предопределенные курсора Windows. Необходимо иметь **#define OEMRESOURCE** перед **#include \<afxwin.h настроек** для получения доступа к **OCR_** константы в WINDOWS. З.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, если выполнено успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте `LoadOEMCursor` или [LoadStandardCursor](#loadstandardcursor) функции-члена для доступа к предварительно определенных курсоров Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#45;](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing&#46;](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="a-nameloadoemicona--cwinapploadoemicon"></a><a name="loadoemicon"></a>CWinApp::LoadOEMIcon  
 Загружает Windows предопределенные значок ресурс, заданный параметром `nIDIcon`.  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nIDIcon`  
 **OIC_** манифеста идентификатор константы, указывающий стандартные значки Windows. Необходимо иметь **#define OEMRESOURCE** перед **#include \<afxwin.h настроек** для доступа к **OIC_** константы в WINDOWS. З.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте `LoadOEMIcon` или [LoadStandardIcon](#loadstandardicon) функции-члена для доступа к предварительно определенных значков Windows.  
  
##  <a name="a-nameloadstandardcursora--cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>CWinApp::LoadStandardCursor  
 Загружает Windows заранее определенных ресурсов курсора, `lpszCursorName` указывает.  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszCursorName`  
 **IDC_** манифеста идентификатор константы, указывающее предопределенные курсора Windows. Эти идентификаторы определяются в WINDOWS. З. Ниже перечислены возможные предопределенные значения и значения для `lpszCursorName`:  
  
- **IDC_ARROW** курсора Стандартная стрелка  
  
- **IDC_IBEAM** курсора Стандартная вставки текста  
  
- **IDC_WAIT** песочные часы курсор, используемый, когда Windows выполняет слишком много времени  
  
- **IDC_CROSS** курсор-перекрестие для выбора  
  
- **IDC_UPARROW** стрелка, указывающая вверх  
  
- **IDC_SIZE** устарела и не поддерживается; используйте **IDC_SIZEALL**  
  
- **IDC_SIZEALL** четырехконечная стрелка. Курсор для изменения размера окна.  
  
- **IDC_ICON** устаревшие и неподдерживаемые. Используйте **IDC_ARROW**.  
  
- **IDC_SIZENWSE** двунаправленную стрелку с заканчивается в верхнем левом и правом нижнем  
  
- **IDC_SIZENESW** двунаправленную стрелку с заканчивается в верхнем левом углу справа и ниже  
  
- **IDC_SIZEWE** горизонтальной двусторонней стрелки  
  
- **IDC_SIZENS** вертикальной двусторонней стрелки  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор курсора, если выполнено успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте `LoadStandardCursor` или [LoadOEMCursor](#loadoemcursor) функции-члена для доступа к предварительно определенных курсоров Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#47;](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="a-nameloadstandardicona--cwinapploadstandardicon"></a><a name="loadstandardicon"></a>CWinApp::LoadStandardIcon  
 Предопределенные Windows загружает ресурс значка, `lpszIconName` указывает.  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpszIconName`  
 Манифеста идентификатор константы, указывающий стандартные значки Windows. Эти идентификаторы определяются в WINDOWS. З. Список предопределенных возможные значения и их описание см. в разделе *lpIconName* параметр в [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для значка в случае успешного выполнения; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Используйте `LoadStandardIcon` или [LoadOEMIcon](#loadoemicon) функции-члена для доступа к предварительно определенных значков Windows.  
  
##  <a name="a-nameloadstdprofilesettingsa--cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>CWinApp::LoadStdProfileSettings  
 Вызвать эту функцию-член из [InitInstance](#initinstance) функция-член для включения и загрузить список недавно использованных файлов (MRU) и последнего предварительного просмотра состояния.  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>Параметры  
 `nMaxMRU`  
 Число недавно использовавшихся файлов для отслеживания.  
  
### <a name="remarks"></a>Примечания  
 Если `nMaxMRU` равно 0, список последних Использованных не будет поддерживаться.  
  
##  <a name="a-namembhelpmodea--cwinappmbhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode  
 **Значение TRUE,** Если приложение находится в режиме контекст справки (обычно вызывается с SHIFT + F1); в противном случае **FALSE**.  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Примечания  
 В режиме контекст справки наклоненного вопросительный знак и пользователь может перемещать о экрана. Проверьте этот флаг, если вы хотите реализовать специальной обработки в режиме справки. `m_bHelpMode`— это открытая переменная типа **BOOL**.  
  
##  <a name="a-namemdwrestartmanagersupportflagsa--cwinappmdwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags  
 Флаги, которые определяют поведение диспетчера перезапуска.  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Примечания  
 Чтобы включить диспетчер перезапуска, установите `m_dwRestartManagerSupportFlags` в желаемое поведение. В следующей таблице показаны доступные флаги.  
  
|||  
|-|-|  
|Flag|Описание|  
|`AFX_RESTART_MANAGER_SUPPORT_RESTART`|Приложение регистрируется с помощью [CWinApp::RegisterWithRestartManager](#registerwithrestartmanager). Диспетчер перезапуска отвечает за перезапуска приложения, если она неожиданно завершает работу.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`|Приложение регистрируется с диспетчером перезапуска и диспетчер перезапуска вызывает функцию обратного вызова для восстановления после его перезапуска приложения. Функция обратного вызова для восстановления по умолчанию является [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`|Эта функция включена и преждевременном диспетчера перезапуска открытые документы после перезапуска приложения.|  
|- `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`|Эта функция включена и преждевременном диспетчера перезапуска открытые документы с определенным интервалом. Интервал определяется [CWinApp::m_nAutosaveInterval](#m_nautosaveinterval).|  
|- `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`|Диспетчер перезапуска открывает ранее открытые документы после перезапуска приложения из непредвиденный выход. [CDataRecoveryHandler класс](../../mfc/reference/cdatarecoveryhandler-class.md) обеспечивает сохранение списка открытых документов и их восстановление.|  
|- `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`|Диспетчер перезапуска предлагает пользователю восстановить файлы автоматически сохраненная после перезапуска приложения. `CDataRecoveryHandler` Класс запросов пользователя.|  
|- `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`|Объединение `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_SUPPORT_RECOVER`, и `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RESTART`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
|- `AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS`|The union of `AFX_RESTART_MANAGER_SUPPORT_RECOVERY`, `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`, `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`, and `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`.|  
  
##  <a name="a-namemehelptypea--cwinappmehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType  
 Тип этого элемента данных — перечислимый тип **AFX_HELP_TYPE**, которая определена в `CWinApp` класса.  
  
```  
AFX_HELP_TYPE m_eHelpType;  
```  
  
### <a name="remarks"></a>Примечания  
 **AFX_HELP_TYPE** перечисление определяется следующим образом:  
  
 `enum AFX_HELP_TYPE`  
  
 `{`  
  
 `afxWinHelp = 0,`  
  
 `afxHTMLHelp = 1`  
  
 `};`  
  
-   Чтобы задать справки приложения для HTML-справки, вызовите [SetHelpMode](#sethelpmode) и укажите **afxHTMLHelp**.  
  
-   Чтобы задать помогают приложения WinHelp, вызовите `SetHelpMode` и укажите **afxWinHelp**.  
  
##  <a name="a-namemhinstancea--cwinappmhinstance"></a><a name="m_hinstance"></a>CWinApp::m_hInstance  
 Соответствует `hInstance` параметр, передаваемый по Windows `WinMain`.  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hInstance` Член данных — это дескриптор для текущего экземпляра приложения, работающие под управлением Windows. Это значение возвращается функцией глобального [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle). `m_hInstance`— это открытая переменная типа `HINSTANCE`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#55;](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="a-namemlpcmdlinea--cwinappmlpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine  
 Соответствует `lpCmdLine` параметр, передаваемый по Windows `WinMain`.  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Примечания  
 Точки нулем строку, которая задает командную строку для приложения. Используйте `m_lpCmdLine` для доступа к аргументы командной строки введенные при запуске приложения пользователем. `m_lpCmdLine`— это открытая переменная типа `LPTSTR`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="a-namemnautosaveintervala--cwinappmnautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval  
 Продолжительность времени в миллисекундах между преждевременном.  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Примечания  
 Можно настроить диспетчер перезапуска для автоматического сохранения открытых документов через заданные интервалы времени. Если приложение не автосохранения, этот параметр не оказывает влияния.  
  
##  <a name="a-namemncmdshowa--cwinappmncmdshow"></a><a name="m_ncmdshow"></a>CWinApp::m_nCmdShow  
 Соответствует `nCmdShow` параметр, передаваемый по Windows `WinMain`.  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо передать `m_nCmdShow` в качестве аргумента при вызове [CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) для главного окна приложения. `m_nCmdShow`— это открытая переменная типа `int`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#56;](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="a-namempactivewnda--cwinappmpactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd  
 Используйте этот элемент данных для хранения указателя в главное окно приложения OLE-контейнера с вашей OLE сервера приложения на месте активации.  
  
### <a name="remarks"></a>Примечания  
 Если этот член данных — **NULL**, приложение не является активным на месте.  
  
 Платформа задает переменную-член, если окно является месте активируется приложением контейнера OLE.  
  
##  <a name="a-namempdatarecoveryhandlera--cwinappmpdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler  
 Указатель на обработчик восстановления данных для приложения.  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Примечания  
 Обработчик восстановления данных приложения отслеживает открытые документы и преждевременном их. Платформа использует обработчик восстановления данных для восстановления файлов автоматически сохраненная при перезапуске приложения после его неожиданно завершает работу. Дополнительные сведения см. в разделе [CDataRecoveryHandler класса](../../mfc/reference/cdatarecoveryhandler-class.md).  
  
##  <a name="a-namempszappnamea--cwinappmpszappname"></a><a name="m_pszappname"></a>CWinApp::m_pszAppName  
 Задает имя приложения.  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Примечания  
 Имя приложения могут поступать из параметр, передаваемый [CWinApp](#cwinapp) конструктор, или, если не указано, на строку ресурса с Идентификатором **AFX_IDS_APP_TITLE**. Если имя приложения не найдено в ресурсе, он поступает из программы. Имя файла EXE.  
  
 Возвращенный глобальную функцию [AfxGetAppName](application-information-and-management.md#afxgetappname). `m_pszAppName`— это открытая переменная типа **const char\***.  
  
> [!NOTE]
>  Если присвоить значение `m_pszAppName`, его необходимо получать динамическое выделение памяти в куче. `CWinApp` Вызывает деструктор **свободного**() этого указателя. Многие необходимо использовать `_tcsdup`функции библиотеки времени выполнения () для этого выделения. Кроме того освободите память, связанную с текущим указателем до назначения нового значения. Например:  
  
 [!code-cpp[NVC_MFCWindowing&#57;](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#65;](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="a-namempszexenamea--cwinappmpszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName  
 Содержит имя исполняемого файла приложения без расширения.  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Примечания  
 В отличие от [m_pszAppName](#m_pszappname), это имя не может содержать пробелы. `m_pszExeName`— это открытая переменная типа **const char\***.  
  
> [!NOTE]
>  Если присвоить значение `m_pszExeName`, его необходимо получать динамическое выделение памяти в куче. `CWinApp` Вызывает деструктор **свободного**() этого указателя. Многие необходимо использовать `_tcsdup`функции библиотеки времени выполнения () для этого выделения. Кроме того освободите память, связанную с текущим указателем до назначения нового значения. Например:  
  
 [!code-cpp[NVC_MFCWindowing&#58;](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="a-namempszhelpfilepatha--cwinappmpszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath  
 Содержит путь к файлу справки приложения.  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Примечания  
 По умолчанию, инициализирует платформа `m_pszHelpFilePath` имя приложения с помощью». HLP» добавляется. Чтобы изменить имя файла справки, установите `m_pszHelpFilePath` для указания строка, содержащая полное имя файла справки нужное. — Удобное место для этого в приложении [InitInstance](#initinstance) функции. `m_pszHelpFilePath`— это открытая переменная типа **const char\***.  
  
> [!NOTE]
>  Если присвоить значение `m_pszHelpFilePath`, его необходимо получать динамическое выделение памяти в куче. `CWinApp` Вызывает деструктор **свободного**() этого указателя. Многие необходимо использовать `_tcsdup`функции библиотеки времени выполнения () для этого выделения. Кроме того освободите память, связанную с текущим указателем до назначения нового значения. Пример:  
  
 [!code-cpp[NVC_MFCWindowing&#59;](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="a-namempszprofilenamea--cwinappmpszprofilename"></a><a name="m_pszprofilename"></a>CWinApp::m_pszProfileName  
 Содержит имя приложения. INI-файл.  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_pszProfileName`— это открытая переменная типа **const char\***.  
  
> [!NOTE]
>  Если присвоить значение `m_pszProfileName`, его необходимо получать динамическое выделение памяти в куче. `CWinApp` Вызывает деструктор **свободного**() этого указателя. Многие необходимо использовать `_tcsdup`функции библиотеки времени выполнения () для этого выделения. Кроме того освободите память, связанную с текущим указателем до назначения нового значения. Пример:  
  
 [!code-cpp[NVC_MFCWindowing&#60;](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="a-namempszregistrykeya--cwinappmpszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey  
 Используется для определения, в реестре или INI-файл приложения профиля хранятся параметры конфигурации.  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Примечания  
 Как правило этот элемент данных обрабатывается только для чтения.  
  
-   Значение, хранящееся в раздел реестра. Имя параметра профиля приложения добавляется следующий раздел реестра: HKEY_CURRENT_USER и программного обеспечения и LocalAppWizard-создаваемые или.  
  
 Если присвоить значение `m_pszRegistryKey`, его необходимо получать динамическое выделение памяти в куче. `CWinApp` Вызывает деструктор **свободного**() этого указателя. Многие необходимо использовать `_tcsdup`функции библиотеки времени выполнения () для этого выделения. Кроме того освободите память, связанную с текущим указателем до назначения нового значения. Например:  
  
 [!code-cpp[NVC_MFCWindowing&#61;](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="a-namempszappida--cwinappmpszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID  
 Идентификатор приложения пользователя модели.  
  
```  
LPCTSTR m_pszAppID;  
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="a-nameoncontexthelpa--cwinapponcontexthelp"></a><a name="oncontexthelp"></a>CWinApp::OnContextHelp  
 Обрабатывает клавиши SHIFT + F1 справки в приложении.  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )` инструкции для вашего `CWinApp` класса схемы сообщений, а также добавить записи в таблице сочетаний клавиш, обычно клавиши SHIFT + F1, чтобы включить эту функцию-член.  
  
 `OnContextHelp`переводит приложение в режим справки. Стрелка и знак вопроса и пользователь может затем наведите указатель мыши и нажмите левую кнопку мыши для выбора диалоговое окно, окно, меню или кнопки. Эта функция-член возвращает контекст справки объекта под курсором и вызывает функцию Windows WinHelp с этим контекстом справки.  
  
##  <a name="a-nameonddecommanda--cwinapponddecommand"></a><a name="onddecommand"></a>CWinApp::OnDDECommand  
 Вызывается платформой, получив DDE фрейма главного окна выполнения сообщения.  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszCommand*  
 Указывает строку команды DDE, полученных приложением.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если команда обрабатывается; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию проверяет, является ли команда запроса на открытие документа и в этом случае открывается указанный документ. Диспетчер файлов обычно отправляет такие строки команд DDE, при двойном щелчке файла данных. Переопределение эту функцию для обработки других DDE выполнение команд, таких как команда для печати.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#48;](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="a-nameonfilenewa--cwinapponfilenew"></a><a name="onfilenew"></a>CWinApp::OnFileNew  
 Реализует `ID_FILE_NEW` команды.  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_FILE_NEW, OnFileNew )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнения файла новой команды.  
  
 В разделе [Технические заметки 22](../../mfc/tn022-standard-commands-implementation.md) сведения на поведение по умолчанию и рекомендации о том, как переопределить эту функцию-член.  
  
### <a name="example"></a>Пример  
 [!code-cpp[№&49; NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonfileopena--cwinapponfileopen"></a><a name="onfileopen"></a>CWinApp::OnFileOpen  
 Реализует `ID_FILE_OPEN` команды.  
  
```  
afx_msg void OnFileOpen();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_FILE_OPEN, OnFileOpen )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнение команды открытия файла.  
  
 Сведения о поведении по умолчанию и рекомендации о том, как переопределить эту функцию-член, в разделе [Технические заметки 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[№&49; NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonfileprintsetupa--cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>CWinApp::OnFilePrintSetup  
 Реализует **ID_FILE_PRINT_SETUP** команды.  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, эта функция обрабатывает выполнение команды печати файла.  
  
 Сведения о поведении по умолчанию и рекомендации о том, как переопределить эту функцию-член, в разделе [Технические заметки 22](../../mfc/tn022-standard-commands-implementation.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[№&49; NVC_MFCWindowing](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#50;](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="a-nameonhelpa--cwinapponhelp"></a><a name="onhelp"></a>CWinApp::OnHelp  
 Обрабатывает справку F1 в приложении (с использованием текущего контекста).  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>Примечания  
 Обычно также добавить запись сочетаний клавиш для клавиши F1. Включение клавиши F1 — только соглашение, не является обязательным требованием.  
  
 Необходимо добавить `ON_COMMAND( ID_HELP, OnHelp )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, при нажатии клавиши F1 вызывается платформой.  
  
 Реализация по умолчанию эта функция обработчика сообщений определяет контекст справки, который соответствует текущее окно, диалоговое окно или элемент меню, а затем вызывает WINHELP. EXE-ФАЙЛ. Если контекст в настоящее время недоступен, функция использует контекст по умолчанию.  
  
 Переопределите эту функцию-член для задания контекста справки на что-нибудь кроме окна, диалоговое окно, пункт меню или кнопки панели инструментов, которая в данный момент имеет фокус. Вызов `WinHelp` с нужной справки идентификатор контекста.  
  
##  <a name="a-nameonhelpfindera--cwinapponhelpfinder"></a><a name="onhelpfinder"></a>CWinApp::OnHelpFinder  
 Обрабатывает **ID_HELP_FINDER** и **ID_DEFAULT_HELP** команды.  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, платформа вызывает функцию этот обработчик сообщений, при выборе пользователем приложения поиска справки команду, чтобы вызвать `WinHelp` со стандартными **HELP_FINDER** раздела.  
  
##  <a name="a-nameonhelpindexa--cwinapponhelpindex"></a><a name="onhelpindex"></a>CWinApp::OnHelpIndex  
 Обрабатывает **ID_HELP_INDEX** команды и предоставляет раздел справки по умолчанию.  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Если параметр включен, платформа вызывает функцию этот обработчик сообщений, при выборе пользователем приложения команду индекс справки, чтобы вызвать `WinHelp` со стандартными **HELP_INDEX** раздела.  
  
##  <a name="a-nameonhelpusinga--cwinapponhelpusing"></a><a name="onhelpusing"></a>CWinApp::OnHelpUsing  
 Обрабатывает **ID_HELP_USING** команды.  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо добавить `ON_COMMAND( ID_HELP_USING, OnHelpUsing )` инструкции для вашего `CWinApp` класс схемы сообщений, чтобы включить эту функцию-член. Платформа вызывает функцию этот обработчик сообщений, при выборе пользователем приложения справку с помощью команды `WinHelp` приложение со стандартными **HELP_HELPONHELP** раздела.  
  
##  <a name="a-nameonidlea--cwinapponidle"></a><a name="onidle"></a>CWinApp::OnIdle  
 Переопределите эту функцию-член для выполнения обработки времени простоя.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>Параметры  
 `lCount`  
 Значение счетчика увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений приложения является пустым. Этот счетчик обнуляется каждый раз при обработке нового сообщения. Можно использовать `lCount` параметр, чтобы определить относительный интервал времени приложения простаивал без обработки сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение для получения более обработки времени простоя; 0, если требуется больше времени простоя.  
  
### <a name="remarks"></a>Примечания  
 `OnIdle`вызывается в цикл обработки сообщений по умолчанию, когда очередь сообщений приложения является пустым. Используйте переопределения для вызова свой опыт простоя обработчика задач.  
  
 `OnIdle`должен возвращать 0, чтобы указать, что нет времени простоя обработки не требуется. `lCount` Параметр увеличивается каждый раз `OnIdle` вызывается, когда очередь сообщений является пустым и сбрасывается в 0 каждый раз при обработке нового сообщения. Можно вызвать другой простоя подпрограмм на основе этого количества.  
  
 Далее перечислены обработка пустых циклов.  
  
1.  Если цикл обработки сообщений в библиотеки классов Microsoft Foundation проверяет очереди сообщений и не находит ожидающих сообщений, он вызывает `OnIdle` для объекта приложения и предоставляет 0 как `lCount` аргумент.  
  
2. `OnIdle`выполняет некоторую обработку и возвращает ненулевое значение, указывающее, она должна быть вызвана снова сделать дальнейшей обработки.  
  
3.  Цикл обработки сообщений снова проверяет очереди сообщений. Если нет сообщений, ожидающих выполнения, он вызывает `OnIdle` , увеличивая `lCount` аргумент.  
  
4.  В конечном счете `OnIdle` завершает обработку его простоя задачи и возвращает 0. В этом случае цикл обработки сообщений для остановки вызова `OnIdle` до получения следующего сообщения из очереди сообщений, на этом этапе цикла простоя перезапускается с аргументом, равным 0.  
  
 Не выполняйте продолжительных задач во время `OnIdle` , поскольку приложение не может обработать входные данные пользователя до `OnIdle` возвращает.  
  
> [!NOTE]
>  Реализация по умолчанию `OnIdle` команды обновления объектов пользовательского интерфейса, например, пункты меню и кнопки панели инструментов, и он выполняет очистку структуры внутренних данных. Таким образом Если переопределить `OnIdle`, необходимо вызвать `CWinApp::OnIdle` с `lCount` в переопределенные версии. Сначала вызовите обработки бездействия все базового класса (то есть до базового класса `OnIdle` возвращает 0). Если необходимо выполнять работу до завершения обработки базового класса, просмотрите реализацию базового класса для выбора соответствующих `lCount` во время которого будет выполняться.  
  
 Если вы не хотите `OnIdle` вызываться всякий раз, когда сообщение извлекается из очереди сообщений, можно переопределить [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage). Если приложение установило таймер с очень короткими или отправка системы **WM_SYSTIMER** сообщения, затем `OnIdle` будет вызываться несколько раз и привести к снижению производительности.  
  
### <a name="example"></a>Пример  
 В следующих двух примерах показано использование `OnIdle`. Первый пример обрабатывает два задачи периода бездействия с помощью `lCount` аргумент, чтобы определить приоритеты задач. Первая задача — высокий приоритет и необходимо сделать это, когда это возможно. Вторая задача менее важно и должно выполняться только в том случае, если Длительные паузы вводимые пользователем данные. Обратите внимание на вызов к версии базового класса `OnIdle`. Во втором примере управляет группы задач периода бездействия системы с различным приоритетом.  
  
 [!code-cpp[NVC_MFCWindowing&#51;](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="a-nameopendocumentfilea--cwinappopendocumentfile"></a><a name="opendocumentfile"></a>CWinApp::OpenDocumentFile  
 Платформа вызывает этот метод для открытия именованного [CDocument](../../mfc/reference/cdocument-class.md) файл для приложения.  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszFileName`  
 Имя файла, который необходимо открыть.  
  
 [in] `bAddToMRU`  
 `TRUE`Указывает, что документ является одним из самых последних версий файлов; `FALSE` указывает документ не является одним из самых последних версий файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CDocument` при успехе; в противном случае `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Если документ с таким именем уже открыт, первое окно фрейма, содержащего этот документ получит фокус. Если приложение поддерживает несколько шаблонов документов, платформа использует расширение имени файла для поиска соответствующего шаблона документа для повторной загрузки документа. В случае успеха документ затем шаблон создает фрейм окна и представления документа.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#52;](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="a-nameparsecommandlinea--cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::ParseCommandLine  
 Вызов этой функции-члена для командной строки и параметров, поочередно, отправить [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam).  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `rCmdInfo`  
 Ссылку на [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 При запуске нового проекта MFC с помощью мастера приложений, мастер приложения создает локальный экземпляр `CCommandLineInfo`, а затем вызвать `ProcessShellCommand` и `ParseCommandLine` в [InitInstance](#initinstance) функции-члена. В командной строке выполняется по маршруту, описанных ниже:  
  
1.  После создания в `InitInstance`, `CCommandLineInfo` передается объект `ParseCommandLine`.  
  
2. `ParseCommandLine`затем вызывает `CCommandLineInfo::ParseParam` несколько раз, один раз для каждого параметра.  
  
3. `ParseParam`заполняет `CCommandLineInfo` объекта, который затем передается [ProcessShellCommand](#processshellcommand).  
  
4. `ProcessShellCommand`обрабатывает аргументы командной строки и флаги.  
  
 Обратите внимание, что может вызвать `ParseCommandLine` непосредственно по мере необходимости.  
  
 Описание флагов командной строки см. в разделе [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand).  
  
##  <a name="a-namepretranslatemessagea--cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>CWinApp::PreTranslateMessage  
 Переопределить эту функцию для фильтрации окна сообщений перед их отправкой в функции Windows [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) и [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) реализация по умолчанию выполняет преобразование сочетаний клавиш, поэтому необходимо вызвать `CWinApp::PreTranslateMessage` переопределенные версии функции-члена.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `pMsg`  
 Указатель на [MSG](../../mfc/reference/msg-structure1.md) структура, содержащая сообщение для обработки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано полностью в `PreTranslateMessage` и не должна обрабатываться Дополнительно. Нуль, если сообщения должны обрабатываться обычным способом.  
  
##  <a name="a-nameprocessmessagefiltera--cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::ProcessMessageFilter  
 Функция-ловушка framework вызывает эту функцию-член для фильтрации и отвечать на определенные сообщения Windows.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>Параметры  
 `code`  
 Указывает код обработчика. Эта функция-член использует код для определения способа обработки`lpMsg.`  
  
 `lpMsg`  
 Указатель на Windows [MSG](../../mfc/reference/msg-structure1.md) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение обработано; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Функция-ловушка обрабатывает события перед отправкой сообщения обычного приложения обработки.  
  
 Если переопределить это дополнительная функция, необходимо вызвать версию базового класса для поддержания framework подключить обработки.  
  
##  <a name="a-nameprocessshellcommanda--cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::ProcessShellCommand  
 Эта функция-член вызывается [InitInstance](#initinstance) принимать параметры, передаваемые из `CCommandLineInfo` объекта, указанного в `rCmdInfo`и выполнить указанное действие.  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>Параметры  
 `rCmdInfo`  
 Ссылку на [CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md) объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно обработала командной оболочки. Если значение равно 0, вернуть **FALSE** из [InitInstance](#initinstance).  
  
### <a name="remarks"></a>Примечания  
 При запуске нового проекта MFC с помощью мастера приложений, мастер приложения создает локальный экземпляр `CCommandLineInfo`, а затем вызвать `ProcessShellCommand` и [ParseCommandLine](#parsecommandline) в `InitInstance` функции-члена. В командной строке выполняется по маршруту, описанных ниже:  
  
1.  После создания в `InitInstance`, `CCommandLineInfo` передается объект `ParseCommandLine`.  
  
2. `ParseCommandLine`затем вызывает [CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam) повторяется один раз для каждого параметра.  
  
3. `ParseParam`заполняет `CCommandLineInfo` объекта, который затем передается `ProcessShellCommand`.  
  
4. `ProcessShellCommand`обрабатывает аргументы командной строки и флаги.  
  
 Члены данных `CCommandLineInfo` объекта, идентифицируемого по [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand), имеют следующий тип перечисления, который определен в `CCommandLineInfo` класса.  
  
 `enum {`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `};`  
  
 Краткое описание каждого из этих значений см. в разделе `CCommandLineInfo::m_nShellCommand`.  
  
##  <a name="a-nameprocesswndprocexceptiona--cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>CWinApp::ProcessWndProcException  
 Платформа вызывает эту функцию-член, всякий раз, когда обработчик не перехватывает исключение, создаваемое в одном из сообщений в приложении или обработчиков команд.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>Параметры  
 *e*  
 Указатель на неперехваченное исключение.  
  
 `pMsg`  
 Объект [MSG](../../mfc/reference/msg-structure1.md) структуру, содержащую сведения о windows сообщения, которое вызвало платформа для создания исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, возвращаемое операционной системе Windows. Обычно это 0L для сообщений windows, 1L ( **TRUE**) для сообщений команды.  
  
### <a name="remarks"></a>Примечания  
 Не следует вызывать функции-члена напрямую.  
  
 Реализация по умолчанию эта функция-член создает окно сообщения. Если неперехваченное исключение происходит с меню, панели инструментов или ошибка команды сочетаний клавиш, в окне сообщения отображается сообщение «Не удалось выполнить команду»; в обратном случае отображается сообщение «Внутренняя ошибка приложения».  
  
 Переопределите эту функцию-член для предоставления глобального обработки исключений. Вызовите базовую функциональность, только при необходимости окно сообщения для отображения.  
  
##  <a name="a-nameregistera--cwinappregister"></a><a name="register"></a>CWinApp::Register  
 Выполняет все задачи регистрации, не обрабатываются `RegisterShellFileTypes`.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию просто возвращает значение TRUE. Переопределите эту функцию для обеспечения регистрации настраиваемые действия.  
  
##  <a name="a-nameregistershellfiletypesa--cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>CWinApp::RegisterShellFileTypes  
 Вызовите эту функцию-член для регистрации всех типов документов в приложении с помощью диспетчера файлов Windows.  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bCompat`  
 `TRUE`Добавление записей регистрации для оболочки команды печати и распечатать, дает пользователям возможность печатать файлы непосредственно из оболочки или перетаскиванием файла объекта принтера. Он также добавляет ключ DefaultIcon. По умолчанию этот параметр является `FALSE` для обеспечения обратной совместимости.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет пользователю открыть файл данных, создаваемых приложением, дважды щелкнув его из диспетчера файлов. Вызов `RegisterShellFileTypes` после вызова [AddDocTemplate](#adddoctemplate) для каждого шаблона документа в приложении. Также вызвать [EnableShellOpen](#enableshellopen) при вызове функции-члена `RegisterShellFileTypes`.  
  
 `RegisterShellFileTypes`выполняет итерацию по списку [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) объектов, что приложение поддерживает и, для каждого шаблона документа добавляет записи в базе данных регистрации Windows поддерживает для сопоставлений файлов. Диспетчер файлов эти записи используются для открытия файла данных, когда пользователь дважды щелкает. Это избавляет от необходимости отправки. REG-файл вместе с приложением.  
  
> [!NOTE]
> `RegisterShellFileTypes`работает, только если пользователь запускает программу с правами администратора. Если программа не имеет прав администратора, его невозможно изменить разделы реестра.  
  
 Если база данных регистрации уже сопоставлено расширение имени файла данного файл другого типа, создается без новой связи. В разделе `CDocTemplate` класса для формата строки, необходимые для регистрации этой информации.  
  
##  <a name="a-nameregisterwithrestartmanagera--cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>CWinApp::RegisterWithRestartManager  
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
|Параметр|Описание|  
|[in] `bRegisterRecoveryCallback`|`TRUE`Указывает, что этот экземпляр приложения использует функцию обратного вызова восстановления; `FALSE` указывает, что нет. Платформа вызывает функцию обратного вызова для восстановления, когда приложение неожиданно завершает работу. Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `strRestartIdentifier`|Уникальная строка, идентифицирующая данного экземпляра диспетчера перезапуска. Идентификатор диспетчера перезапуска является уникальным для каждого экземпляра приложения.|  
|[in] `pwzCommandLineArgs`|Строка, содержащая дополнительных аргументов из командной строки.|  
|[in] `dwRestartFlags`|Необязательные флаги диспетчера перезапуска. Дополнительные сведения см. в разделе "Примечания".|  
|[in] `pRecoveryCallback`|Функция обратного вызова восстановления. Эта функция должна принимать `LPVOID` параметр в виде входных данных и возврат `DWORD`. Функция обратного вызова для восстановления по умолчанию является `CWinApp::ApplicationRecoveryCallback`.|  
|[in] `lpvParam`|Входной параметр для восстановления функции обратного вызова. Дополнительные сведения см. в разделе [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback).|  
|[in] `dwPingInterval`|Длина время ожидания диспетчера перезапуска для восстановления функции обратного вызова для возврата. Этот параметр указывается в миллисекундах.|  
|[in] `dwCallbackFlags`|Флаги, передаваемые функции обратного вызова для восстановления. Зарезервировано для будущего использования.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `S_OK`Если метод выполнен успешно; в противном случае — код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Если приложение использует MFC реализация по умолчанию для файлов автосохранения, следует использовать простую версию `RegisterWithRestartManager`. Использование сложных версии `RegisterWithRestartManager` Если вы хотите настроить Автосохранение поведение приложения.  
  
 При вызове этого метода с пустой строкой для `strRestartIdentifier`, `RegisterWithRestartManager` создает строку уникальный идентификатор для данного экземпляра перезапуска диспетчера.  
  
 Когда приложение неожиданно завершает работу, диспетчер перезапуска перезапускает приложение из командной строки и предоставляет уникальный идентификатор в качестве дополнительного аргумента перезапустите. В этом случае платформа вызывает `RegisterWithRestartManager` два раза. Первый вызов поступают из [CWinApp::InitInstance](#initinstance) с пустой строкой идентификатора строки. Затем метод [CWinApp::ProcessShellCommand](#processshellcommand) вызовы `RegisterWithRestartManager` с перезапуска уникальный идентификатор.  
  
 После регистрации приложения с диспетчером перезапуска диспетчера перезапуска отслеживание приложения. Если приложение неожиданно завершает работу, диспетчер перезапуска вызывает функцию обратного вызова восстановления во время процесса завершается. Ожидание диспетчера перезапуска `dwPingInterval` ответа от восстановления функции обратного вызова. Если функция обратного вызова восстановления не отвечает в течение этого времени, приложение завершает работу без выполнения функции обратного вызова для восстановления.  
  
 По умолчанию dwRestartFlags не поддерживаются, но предназначены для использования в будущем. Возможные значения параметра `dwRestartFlags` выглядят следующим образом:  
  
- `RESTART_NO_CRASH`  
  
- `RESTART_NO_HANG`  
  
- `RESTART_NO_PATCH`  
  
- `RESTART_NO_REBOOT`  
  
##  <a name="a-namereopenpreviousfilesatrestarta--cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::ReopenPreviousFilesAtRestart  
 Определяет, открывается ли файлы, которые были открыты, когда приложение неожиданно завершили работу, диспетчер перезапуска.  
  
```  
virtual BOOL ReopenPreviousFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, открывается диспетчер перезапуска ранее открытые файлы; `FALSE` указывает диспетчер перезапуска — нет.  
  
##  <a name="a-namerestartinstancea--cwinapprestartinstance"></a><a name="restartinstance"></a>CWinApp::RestartInstance  
 Обрабатывает инициировано диспетчера перезапуска перезапуск приложения.  
  
```  
virtual BOOL CWinApp::RestartInstance();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если обработчик восстановления данных открывает ранее откройте документы; `FALSE` Если обработчик восстановления данных содержит ошибку или нет ранее открытых документов.  
  
### <a name="remarks"></a>Примечания  
 При повторном запуске диспетчера перезапуска приложения платформа вызывает этот метод. Этот метод извлекает обработчик восстановления данных и восстанавливает файлы автоматически сохраненная. Этот метод вызывает метод [CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments) для определения ли пользователю необходимо восстановить файлы автоматически сохраненная.  
  
 Этот метод возвращает `FALSE` Если [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md) определяет, что были нет открытых документов. Если нет открытых документов, обычно запуска приложения.  
  
##  <a name="a-namerestoreautosavedfilesatrestarta--cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::RestoreAutosavedFilesAtRestart  
 Определяет, восстанавливает ли диспетчер перезапуска автоматически сохраненная файлов после его перезапуска приложения.  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает файлы автоматически сохраненная восстановление диспетчера перезапуска; `FALSE` указывает диспетчер перезапуска — нет.  
  
##  <a name="a-nameruna--cwinapprun"></a><a name="run"></a>CWinApp::Run  
 Обеспечивает цикла сообщений по умолчанию.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `int` Значение, возвращенное методом `WinMain`.  
  
### <a name="remarks"></a>Примечания  
 **Запустите** получает и отправляет сообщения Windows, пока приложение не получит **WM_QUIT** сообщений. Если очередь сообщений приложения в настоящее время не содержит сообщений, **запуска** вызовов [OnIdle](#onidle) для выполнения обработки времени простоя. Входящие сообщения попадают в [PreTranslateMessage](#pretranslatemessage) функции-члена для специальной обработки, а затем в функции Windows **TranslateMessage** для перевода стандартной клавиатуры; Наконец, **DispatchMessage** вызывается функция Windows.  
  
 **Запустите** переопределяется редко, но его можно переопределить для предоставления особого поведения.  
  
##  <a name="a-namerunautomateda--cwinapprunautomated"></a><a name="runautomated"></a>CWinApp::RunAutomated  
 Эта функция вызывается для определения ли « **/Automation**«или» **-автоматизации**«параметр присутствует, которое указывает, была ли запущена клиентским приложением серверного приложения.  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если параметр был найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если имеется, параметр удаляется из командной строки. Дополнительные сведения об OLE-автоматизации см. в статье [серверы автоматизации](../../mfc/automation-servers.md).  
  
##  <a name="a-namerunembeddeda--cwinapprunembedded"></a><a name="runembedded"></a>CWinApp::RunEmbedded  
 Эта функция вызывается для определения ли « **и внедрение**«или» **-Embedding**» параметр присутствует, которое указывает, была ли запущена клиентским приложением серверного приложения.  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если параметр был найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если имеется, параметр удаляется из командной строки. Дополнительные сведения о внедрении см. в статье [серверы: реализация сервера](../../mfc/servers-implementing-a-server.md).  
  
##  <a name="a-namesaveallmodifieda--cwinappsaveallmodified"></a><a name="saveallmodified"></a>CWinApp::SaveAllModified  
 Вызывается средой для сохранения всех документов, когда закрывается фрейма главного окна приложения или с помощью `WM_QUERYENDSESSION` сообщения.  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если безопасный завершить работу приложения; 0, если это не безопасно завершить приложение.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция-член вызывает [CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified) функции-члена в свою очередь для всех измененных документов в приложении.  
  
##  <a name="a-nameselectprintera--cwinappselectprinter"></a><a name="selectprinter"></a>CWinApp::SelectPrinter  
 Вызовите эту функцию-член, чтобы выбрать принтер и отпустите принтер, который ранее был выбран в диалоговом окне печати.  
  
```  
void SelectPrinter(
    HANDLE hDevNames,  
    HANDLE hDevMode,  
    BOOL bFreeOld = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `hDevNames`  
 Дескриптор [DEVNAMES](../../mfc/reference/devnames-structure.md) структура, определяющая драйвера, устройства и имена портов вывода конкретного принтера.  
  
 `hDevMode`  
 Дескриптор [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) структура, которая задает сведения об инициализации устройства и среде принтера.  
  
 *bFreeOld*  
 Освобождает ранее выбранный принтер.  
  
### <a name="remarks"></a>Примечания  
 Если оба `hDevMode` и `hDevNames` , **NULL**, `SelectPrinter` использует текущий принтер по умолчанию.  
  
##  <a name="a-namesethelpmodea--cwinappsethelpmode"></a><a name="sethelpmode"></a>CWinApp::SetHelpMode  
 Задает тип справки приложения.  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>Параметры  
 `eHelpType`  
 Указывает тип справочной системы для использования. В разделе [CWinApp::m_eHelpType](#m_ehelptype) для получения дополнительной информации.  
  
### <a name="remarks"></a>Примечания  
 Задает тип справки приложения.  
  
 Задайте тип справки приложения HTMLHelp, можно последовательно вызвать методы [EnableHTMLHelp](#enablehtmlhelp). При вызове метода `EnableHTMLHelp`, приложение должно использовать HTMLHelp как его приложение справки. Если требуется изменить для использования WinHelp, можно вызвать `SetHelpMode` и `eHelpType` для **afxWinHelp**.  
  
##  <a name="a-namesetregistrykeya--cwinappsetregistrykey"></a><a name="setregistrykey"></a>CWinApp::SetRegistryKey  
 В результате приложения параметры хранятся в реестре, вместо INI-файлы.  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszRegistryKey*  
 Указатель на строку, содержащую имя ключа.  
  
 *nIDRegistryKey*  
 Идентификатор строкового ресурса, содержащее имя раздела реестра.  
  
### <a name="remarks"></a>Примечания  
 Эта функция задает *m_pszRegistryKey*, который затем используется для `GetProfileInt`, `GetProfileString`, `WriteProfileInt`, и `WriteProfileString` функции-члены класса `CWinApp`. При вызове этой функции в реестре также хранится список последних использовавшихся файлов (MRU). Раздел реестра обычно является название компании. Он хранится в ключе в следующей форме: HKEY_CURRENT_USER\Software\\<company></company>\>\\<application></application>\>\\<section></section>\>\\<value></value>\>.  
  
##  <a name="a-namesupportsapplicationrecoverya--cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>CWinApp::SupportsApplicationRecovery  
 Определяет, восстанавливает ли диспетчер перезапуска приложения, неожиданно завершили работу.  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, выполнено восстановление диспетчера перезапуска приложения; `FALSE` указывает диспетчер перезапуска — нет.  
  
##  <a name="a-namesupportsautosaveatintervala--cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::SupportsAutosaveAtInterval  
 Определяет ли преждевременном диспетчера перезапуска открывать документы с определенным интервалом.  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что преждевременном диспетчера перезапуска открывать документы; `FALSE` указывает диспетчер перезапуска — нет.  
  
##  <a name="a-namesupportsautosaveatrestarta--cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::SupportsAutosaveAtRestart  
 Определяет, является ли преждевременном диспетчера перезапуска открытые документы после перезапуска приложения.  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что преждевременном диспетчера перезапуска открывать документы при перезапуске приложения; `FALSE` указывает диспетчер перезапуска — нет.  
  
##  <a name="a-namesupportsrestartmanagera--cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>CWinApp::SupportsRestartManager  
 Определяет, поддерживает ли приложение диспетчера перезапуска.  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Указывает, что приложение поддерживает диспетчер перезапуска; `FALSE` указывает не поддерживает приложение.  
  
##  <a name="a-nameunregistera--cwinappunregister"></a><a name="unregister"></a>CWinApp::Unregister  
 Отменяет регистрацию всех файлов зарегистрированных объектов приложения.  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — значение 0.  
  
### <a name="remarks"></a>Примечания  
 `Unregister` Функция отменяет процесс регистрации, выполняемый объект приложения и [зарегистрировать](#register) функции. Как правило обе функции вызываются неявно MFC и поэтому он не будет отображаться в коде.  
  
 Переопределите эту функцию для отмены регистрации пользовательского действия.  
  
##  <a name="a-nameunregistershellfiletypesa--cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::UnregisterShellFileTypes  
 Вызовите эту функцию-член отменить регистрацию всех типов документов в приложении с помощью диспетчера файлов Windows.  
  
```  
void UnregisterShellFileTypes();
```  
  
##  <a name="a-namewinhelpa--cwinappwinhelp"></a><a name="winhelp"></a>CWinApp::WinHelp  
 Вызов этой функции-члена для вызова приложения WinHelp.  
  
```  
virtual void WinHelp(
    DWORD_PTR dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>Параметры  
 `dwData`  
 Задает дополнительные данные. Значение, которое используется зависит от значения `nCmd` параметр.  
  
 `nCmd`  
 Задает тип запрошенной справки. Список возможных значений и их влияние на `dwData` параметр в разделе [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) функции Windows.  
  
### <a name="remarks"></a>Примечания  
 Кроме того, платформа вызывает эту функцию для вызова приложения WinHelp.  
  
 Платформа автоматически закроет приложение WinHelp, когда приложение завершает работу.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#53;](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="a-namewriteprofilebinarya--cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>CWinApp::WriteProfileBinary  
 Вызов этой функции-члена для записи двоичных данных в указанный раздел реестра приложения или. INI-файл.  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Указывает нулем строка, указывающая раздела, содержащего запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.  
  
 `lpszEntry`  
 Точки нулем строку, которая содержит элемент, в который будет записываться значение. Если запись не существует в указанном разделе, он создается.  
  
 `pData`  
 Указатель на записываемые данные.  
  
 `nBytes`  
 Содержит число байтов для записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 В этом примере используется `CWinApp* pApp = AfxGetApp();` получить класс CWinApp, демонстрирующий способ, `WriteProfileBinary` и `GetProfileBinary` можно использовать из любой функции в приложении MFC.  
  
 [!code-cpp[NVC_MFCWindowing&#54;](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 Другой пример, см. пример для [CWinApp::GetProfileBinary](#getprofilebinary).  
  
##  <a name="a-namewriteprofileinta--cwinappwriteprofileint"></a><a name="writeprofileint"></a>CWinApp::WriteProfileInt  
 Вызов этой функции-члена для записи указанное значение в указанный раздел реестра приложения или. INI-файл.  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Указывает нулем строка, указывающая раздела, содержащего запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.  
  
 `lpszEntry`  
 Точки нулем строку, которая содержит элемент, в который будет записываться значение. Если запись не существует в указанном разделе, он создается.  
  
 `nValue`  
 Содержит значение для записи.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 В этом примере используется `CWinApp* pApp = AfxGetApp();` получить класс CWinApp, демонстрирующий способ, `WriteProfileString`, `WriteProfileInt`, `GetProfileString`, и `GetProfileInt` можно использовать из любой функции в приложении MFC.  
  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Другой пример, см. пример для [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namewriteprofilestringa--cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>CWinApp::WriteProfileString  
 Вызов этой функции-члена для Записывает указанную строку в указанный раздел реестра приложения или. INI-файл.  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszSection`  
 Указывает нулем строка, указывающая раздела, содержащего запись. Если раздел не существует, он создается. Имя раздела является случай независимых; Строка может быть любое сочетание прописных и строчных букв.  
  
 `lpszEntry`  
 Точки нулем строку, которая содержит элемент, в который будет записываться значение. Если запись не существует в указанном разделе, он создается. Если этот параметр равен `NULL`, разделе, указанном параметром `lpszSection` удаляется.  
  
 `lpszValue`  
 Указывает строку для записи. Если этот параметр равен `NULL`, запись, указанная параметром `lpszEntry` параметр удаляется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing&#43;](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 Другой пример, см. пример для [CWinApp::GetProfileInt](#getprofileint).  
  
##  <a name="a-namesetappida--cwinappsetappid"></a><a name="setappid"></a>CWinApp::SetAppID  
 Явно задает идентификатор модели приложения пользователя для приложения. Этот метод должен вызываться перед любой пользовательский интерфейс предоставляется пользователю (лучше всего — конструктор приложений).  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcszAppID`  
 Задает идентификатор модели приложения пользователя.  
  
### <a name="remarks"></a>Примечания  
  
## <a name="see-also"></a>См. также  
 [CWinThread-класс](../../mfc/reference/cwinthread-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Практическое руководство: Добавление поддержки диспетчера перезапуска](../../mfc/how-to-add-restart-manager-support.md)




