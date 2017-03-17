---
title: "Класс CInternetSession | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
dev_langs:
- C++
helpviewer_keywords:
- CInternetSession class
- Internet sessions
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
caps.latest.revision: 25
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
ms.openlocfilehash: caec3ae416dc82d49fc0051f0d9d1d2e021e0ba5
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetsession-class"></a>Класс CInternetSession
Создает и инициализирует один или несколько параллельных сеансов Интернета и, при необходимости, описывает подключение к прокси-серверу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetSession : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetSession::CInternetSession](#cinternetsession)|Создает объект `CInternetSession`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetSession::Close](#close)|Закрывает подключение к Интернету при завершении сеанса Интернета.|  
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Устанавливает состояние подпрограммы обратного вызова.|  
|[CInternetSession::GetContext](#getcontext)|Закрывает подключение к Интернету при завершении сеанса Интернета.|  
|[CInternetSession::GetCookie](#getcookie)|Возвращает файлы cookie для указанного URL-адреса и его родительский URL-адреса.|  
|[CInternetSession::GetCookieLength](#getcookielength)|Извлекает переменную, задающее длину файла cookie, хранящиеся в буфере.|  
|[CInternetSession::GetFtpConnection](#getftpconnection)|Откроется FTP-сеанс с сервером. Осуществляет вход пользователя.|  
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Открывает gopher-сервер для приложения, которое пытается установить соединение.|  
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Откроется сервер HTTP для приложения, которое пытается установить соединение.|  
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Обновляет состояние операции, когда включен обратный вызов.|  
|[CInternetSession::OpenURL](#openurl)|Выполняет синтаксический анализ и открывает URL-адрес.|  
|[CInternetSession::SetCookie](#setcookie)|Задает файл cookie для указанного URL-адреса.|  
|[CInternetSession::SetOption](#setoption)|Задает параметры для Интернет-сеанс.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Дескриптор текущего сеанса Интернета.|  
  
## <a name="remarks"></a>Примечания  
 Если подключение к Интернету должны поддерживаться в течение всего приложения, можно создать `CInternetSession` член класса [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 После установления сеанса Интернет можно вызвать [OpenURL](#openurl). `CInternetSession`разбор URL-адрес можно, вызвав функцию глобального [AfxParseURL](http://msdn.microsoft.com/library/505c717e-aa52-4106-8522-eedff3d9bbae). Независимо от его типа протокола `CInternetSession` интерпретирует URL-адрес и он управляет. Он может обрабатывать запросы для локальных файлов с URL-адреса ресурса «file://». `OpenURL`Возвращает указатель на [CStdioFile](../../mfc/reference/cstdiofile-class.md) объекта, передавая имя он является локальным файлом.  
  
 Если открыть URL-адрес на сервере Интернета с помощью `OpenURL`, может считывать сведения из сайта. Если вы хотите выполнять действия определенной службы (для примера, HTTP, FTP, gopher или) файлов, расположенных на сервере, необходимо установить соответствующее соединение с этим сервером. Чтобы открыть конкретный вид подключения непосредственно к определенной службе, воспользуйтесь одним из следующих функций-членов.  
  
- [GetGopherConnection](#getgopherconnection) открыть подключение к службе gopher.  
  
- [GetHttpConnection](#gethttpconnection) открыть подключение к службе HTTP.  
  
- [GetFtpConnection](#getftpconnection) открытие подключения к службе FTP.  
  
 [SetOption](#setoption) позволяет задать параметры запроса сеанса, например значения времени ожидания, число повторных попыток и т. д.  
  
 `CInternetSession`функции-члены [SetCookie](#setcookie), [GetCookie](#getcookie), и [GetCookieLength](#getcookielength) предоставляют средства для управления базой данных cookie Win32, через который серверов и сценарии отслеживания сведений о состоянии о клиентской рабочей станции.  
  
 Дополнительные сведения об основных задачах программирования Интернет см. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md). Общие сведения об использовании классов MFC WinInet см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
> `CInternetSession`вызывает исключение [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) для типов служб не поддерживается. В настоящее время поддерживаются только следующие типы службы: FTP, HTTP, gopher и файл.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cinternetsession"></a>CInternetSession::CInternetSession  
 Эта функция-член вызывается `CInternetSession` создается объект.  
  
```  
CInternetSession(
    LPCTSTR pstrAgent = NULL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,  
    LPCTSTR pstrProxyName = NULL,  
    LPCTSTR pstrProxyBypass = NULL,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrAgent`  
 Указатель на строку, которая идентифицирует имя приложения или сущности, вызов функций Интернета (например, «Microsoft обозревателя»). Если `pstrAgent` — **NULL** (по умолчанию), платформа вызывает функцию глобального [AfxGetAppName](application-information-and-management.md#afxgetappname), который возвращает нулем строка, содержащая имя приложения. Некоторые протоколы использовать эту строку для идентификации приложения на сервер.  
  
 `dwContext`  
 Идентификатор контекста для операции. `dwContext`Определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](#onstatuscallback). По умолчанию используется значение 1; Однако можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связан с этим идентификатором контекста.  
  
 `dwAccessType`  
 Тип доступа. Ниже приведены допустимые значения, только один из которых может быть предоставлен.  
  
- **INTERNET_OPEN_TYPE_PRECONFIG** подключиться с помощью предварительно настроенных параметров в реестре. Этот тип доступа устанавливается по умолчанию. Подключение через прокси-сервер еще ПРИВЛЕКАТЕЛЬНЕЕ, задайте `dwAccessType` значению; затем устанавливается реестра соответствующим образом.  
  
- `INTERNET_OPEN_TYPE_DIRECT`Непосредственное подключение к Интернету.  
  
- `INTERNET_OPEN_TYPE_PROXY`Подключение через прокси-сервер CERN.  
  
 Сведения о подключении с помощью различных типов учетных записей-посредников см [действия в обычном клиентском приложении FTP](../../mfc/steps-in-a-typical-ftp-client-application.md).  
  
 *pstrProxyName*  
 Имя предпочтительного прокси-сервер CERN Если `dwAccessType` задается как `INTERNET_OPEN_TYPE_PROXY`. Значение по умолчанию — **NULL**.  
  
 *pstrProxyBypass*  
 Указатель на строку, содержащую необязательный список адресов серверов. Эти адреса могут обходить при использовании прокси-сервера доступа. Если **NULL** указано значение, список пропускаемых будет считать из реестра. Этот параметр имеет смысл только если `dwAccessType` равен `INTERNET_OPEN_TYPE_PROXY`.  
  
 `dwFlags`  
 Указывает различные параметры кэширования. По умолчанию используется значение 0. Возможные значения:  
  
- `INTERNET_FLAG_DONT_CACHE`Не следует кэшировать данные локально или на все серверы шлюза.  
  
- `INTERNET_FLAG_OFFLINE`Загрузка операций выполняется через только постоянный кэш. Если элемент не существует в кэше, возвращается соответствующего кода ошибки. Этот флаг может объединяться с битовой `OR` ( **|**) оператор.  
  
### <a name="remarks"></a>Примечания  
 **CInternetSession** является первой функции Internet вызывается приложением. Он инициализирует внутренних структур данных и подготавливает для будущих вызовов из приложения.  
  
 Если отсутствует подключение к Интернету может быть открыт, `CInternetSession` вызывает [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
### <a name="example"></a>Пример  
  В примере показано [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="close"></a>CInternetSession::Close  
 Вызовите эту функцию-член по завершении приложения с помощью `CInternetSession` объекта.  
  
```  
virtual void Close();
```  
  
### <a name="example"></a>Пример  
  В примере показано [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="enablestatuscallback"></a>CInternetSession::EnableStatusCallback  
 Вызовите эту функцию-член для включения состояния обратного вызова.  
  
```  
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 `bEnable`  
 Указывает, включен ли обратного вызова. Значение по умолчанию — **TRUE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 При обработке обратного вызова состояние, можно указать состояние хода выполнения операции (например, разрешения имени, подключение к серверу и т. д) в строке состояния приложения. Отображение состояния операции желательно особенно во время операции долгосрочного.  
  
 Поскольку обратные вызовы происходят во время обработки запроса, приложение следует уделить как меньше времени в обратном вызове, для предотвращения снижения пропускную способность сети. Например помещая диалоговое окно с помощью обратного вызова может быть таких длительной операции, что сервер завершает запрос.  
  
 Обратный вызов состояния нельзя удалить до тех пор, пока для любых обратных вызовов, ожидающих выполнения.  
  
 Асинхронная обработка любых операций, необходимо создать собственный поток или используют функции WinInet без использования MFC.  
  
##  <a name="getcontext"></a>CInternetSession::GetContext  
 Вызовите эту функцию-член для получения значения контекста сеанса конкретного приложения.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приложения контекст, определяемый идентификатором.  
  
### <a name="remarks"></a>Примечания  
 [OnStatusCallback](#onstatuscallback) использует возвращенный идентификатор контекста **GetContext** для уведомления о состоянии конкретного приложения. Например когда пользователь активирует Интернет-запрос, который включает в себя возвращения информации о состоянии, обратный вызов состояния использует идентификатор контекста для отчета о состоянии на определенный запрос. Если пользователь активирует два отдельных Internet запрашивает оба варианта связаны возвращения информации о состоянии, `OnStatusCallback` использует идентификаторы контекста для возврата об их соответствующие запросы. Таким образом идентификатор контекста используется для всех операций обратного вызова состояние, и она связана с сеансом до окончания сеанса.  
  
 Дополнительные сведения об асинхронных операциях см. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="getcookie"></a>CInternetSession::GetCookie  
 Эта функция-член реализует поведение функции Win32 [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPTSTR pstrCookieData,  
    DWORD dwBufLen);

 
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    CString& strCookieData);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrUrl`  
 Указатель на строку, содержащую URL-адрес.  
  
 `pstrCookieName`  
 Указатель на строку, содержащую имя файла cookie для получения указанный URL-адрес.  
  
 `pstrCookieData`  
 В первой перегрузке указатель на строку, содержащую адрес буфера, который получает данные файла cookie. Это значение может быть **NULL**. Во второй перегрузке ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект для получения данных файла cookie.  
  
 `dwBufLen`  
 Указав размер переменной `pstrCookieData` буфера. Если функция выполняется успешно, помещаемых в буфер, объем данных, копируемых в `pstrCookieData` буфера. Если `pstrCookieData` — **NULL**, этот параметр получает значение, указывающее размер буфера, необходимый для копирования всех данных файла cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения или **FALSE** в противном случае. Если вызов завершается сбоем, вызовите функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) для определения причины ошибки. Применяются следующие значения ошибки.  
  
- **ERROR_NO_MORE_ITEMS** объекты cookie не указанный URL-адрес и всех его родительских элементов.  
  
- **ERROR_INSUFFICIENT_BUFFER** значение, передаваемое в `dwBufLen` недостаточно скопировать все данные файла cookie. Значение, возвращаемое в `dwBufLen` — это размер буфера для получения всех данных.  
  
### <a name="remarks"></a>Примечания  
 Во второй перегрузке MFC извлекает данные cookie в предоставленной `CString` объекта.  
  
##  <a name="getcookielength"></a>CInternetSession::GetCookieLength  
 Вызовите эту функцию-член получить длину файла cookie в буфере.  
  
```  
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrUrl`  
 Указатель на строку, содержащую URL-адрес  
  
 `pstrCookieName`  
 Указатель на строку, содержащую имя файла cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 A `DWORD` значение, указывающее длину файла cookie, хранящиеся в буфере. Нуль, если нет файла cookie с именем, обозначенными `pstrCookieName` существует.  
  
### <a name="remarks"></a>Примечания  
 Это значение используется [GetCookie](#getcookie).  
  
##  <a name="getftpconnection"></a>CInternetSession::GetFtpConnection  
 Вызов этой функции-члена для установления подключения FTP и получить указатель на `CFtpConnection` объект.  
  
```  
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrServer`  
 Указатель на строку, содержащую имя FTP-сервера.  
  
 `pstrUserName`  
 Указатель на строку с завершающим нулем, указывающее имя пользователя для входа. Если **NULL**, значение по умолчанию является анонимным.  
  
 `pstrPassword`  
 Указатель нулем строку, которая указывает пароль, используемый для входа. Если оба `pstrPassword` и `pstrUserName` , **NULL**, анонимных паролей по умолчанию является имя электронной почты пользователя. Если `pstrPassword` — **NULL** (или пустую строку), но `pstrUserName` не **NULL**, используется пустой пароль. В следующей таблице описаны поведения четыре возможные параметры `pstrUserName` и `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|Имя пользователя передается серверу FTP|Пароль передается серверу FTP|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** или «»|**NULL** или «»|«anonymous»|Имя пользователя электронной почты|  
|Не- **NULL** строки|**NULL** или «»|`pstrUserName`|" "|  
|**NULL** отличных **NULL** строки|**ОШИБКА**|**ОШИБКА**||  
|Не- **NULL** строки|Не- **NULL** строки|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Число, идентифицирующее порт TCP/IP, используемый на сервере.  
  
 `bPassive`  
 Задает пассивный или активный режим для этого сеанса FTP. Если значение **TRUE**, он задает Win32 API `dwFlag` для **INTERNET_FLAG_PASSIVE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CFtpConnection](../../mfc/reference/cftpconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `GetFtpConnection`подключается к FTP-серверу и создает и возвращает указатель на **CFTPConnection** объекта. Он не выполняет любой конкретной операции на сервере. Если требуется считывать или записывать файлы, например, необходимо выполнить эти операции отдельно. В разделе классы [CFtpConnection](../../mfc/reference/cftpconnection-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач подключения FTP.  
  
### <a name="example"></a>Пример  
  В примере показано [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="getgopherconnection"></a>CInternetSession::GetGopherConnection  
 Вызов этой функции-члена для установления нового подключения gopher и получить указатель на `CGopherConnection` объект.  
  
```  
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера gopher.  
  
 `pstrUserName`  
 Указатель на строку, содержащую имя пользователя.  
  
 `pstrPassword`  
 Указатель на строку, содержащую пароль доступа.  
  
 `nPort`  
 Число, идентифицирующее порт TCP/IP, используемый на сервере.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `GetGopherConnection`подключается к серверу gopher и создает и возвращает указатель на `CGopherConnection` объект. Он не выполняет любой конкретной операции на сервере. Если требуется прочитать или записать данные, например, необходимо выполнить эти операции как отдельные шаги. В разделе классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), и [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. Сведения о просмотре FTP-узла см. функция-член [OpenURL](#openurl). См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач подключения gopher.  
  
##  <a name="gethttpconnection"></a>CInternetSession::GetHttpConnection  
 Вызов этой функции-члена для установки подключения HTTP и получить указатель на `CHttpConnection` объект.  
  
```  
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);

 
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера HTTP.  
  
 `nPort`  
 Число, идентифицирующее порт TCP/IP, используемый на сервере.  
  
 `pstrUserName`  
 Указатель на строку, содержащую имя пользователя.  
  
 `pstrPassword`  
 Указатель на строку, содержащую пароль доступа.  
  
 *dwFlags*  
 Любое сочетание **INTERNET_ FLAG_\* ** флаги. См. в таблице **примечания** раздел [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) описание `dwFlags` значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `GetHttpConnection`подключается к серверу HTTP и создает и возвращает указатель на `CHttpConnection` объект. Он не выполняет любой конкретной операции на сервере. Если планируется запрос HTTP-заголовок, например, необходимо выполнить эту операцию как отдельный шаг. В разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) сведения об операциях, можно выполнять с помощью подключения к HTTP-серверу. Сведения о просмотре на HTTP-сайте см. функция-член [OpenURL](#openurl). См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач подключения HTTP.  
  
##  <a name="onstatuscallback"></a>CInternetSession::OnStatusCallback  
 Эта функция-член вызывается платформой для обновления состояния, когда включен обратный вызов, и операция находится в состоянии ожидания.  
  
```  
virtual void OnStatusCallback(
    DWORD_PTR dwContext,  
    DWORD dwInternetStatus,  
    LPVOID lpvStatusInformation,  
    DWORD dwStatusInformationLength);
```  
  
### <a name="parameters"></a>Параметры  
 `dwContext`  
 Значение контекста, предоставляемой приложением.  
  
 `dwInternetStatus`  
 Код состояния, указывающий причину обратного вызова. В разделе **примечания** для таблицы возможных значений.  
  
 `lpvStatusInformation`  
 Указатель на буфер, содержащий сведения, относящиеся к этой функции обратного вызова.  
  
 `dwStatusInformationLength`  
 Размер `lpvStatusInformation`.  
  
### <a name="remarks"></a>Примечания  
 Во-первых, необходимо вызвать [EnableStatusCallback](#enablestatuscallback) преимуществами обратного вызова состояние.  
  
 `dwInternetStatus` Параметр указывает выполняемой операции и определяет, какое содержимое `lpvStatusInformation` будет. `dwStatusInformationLength`Указывает длину данных, содержащихся в `lpvStatusInformation`. Значения состояния `dwInternetStatus` определяется следующим образом:  
  
|Значение|Значение|  
|-----------|-------------|  
|`INTERNET_STATUS_RESOLVING_NAME`|Поиск IP-адреса с именем, содержащимся в `lpvStatusInformation`.|  
|`INTERNET_STATUS_NAME_RESOLVED`|Успешно найден IP-адрес с именем, содержащимся в `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Подключение к адресу сокета ( [SOCKADDR](../../mfc/reference/sockaddr-structure.md)) указывает `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Успешное подключение к адресу сокета ( `SOCKADDR`) указывает `lpvStatusInformation`.|  
|`INTERNET_STATUS_SENDING_REQUEST`|Отправка запроса сведения на сервер. `lpvStatusInformation` Параметр **NULL**.|  
|**INTERNET_STATUS_ REQUEST_SENT**|Успешно отправлен запрос на сведения о сервере. `lpvStatusInformation` Параметр **NULL**.|  
|`INTERNET_STATUS_RECEIVING_RESPONSE`|Ожидание ответа на запрос сервера. `lpvStatusInformation` Параметр **NULL**.|  
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Успешно получил ответ от сервера. `lpvStatusInformation` Параметр **NULL**.|  
|`INTERNET_STATUS_CLOSING_CONNECTION`|Закрытие подключения к серверу. `lpvStatusInformation` Параметр **NULL**.|  
|`INTERNET_STATUS_CONNECTION_CLOSED`|Подключение к серверу успешно закрыто. `lpvStatusInformation` Параметр **NULL**.|  
|`INTERNET_STATUS_HANDLE_CREATED`|Используемые функции Win32 API [InternetConnect](http://msdn.microsoft.com/library/windows/desktop/aa384363) для указания, что он создал новый маркер. Это позволяет функции вызова Win32 приложения [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) из другого потока, если подключение выполняется слишком долго. В разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]Дополнительные сведения об этих функциях.|  
|`INTERNET_STATUS_HANDLE_CLOSING`|Успешно завершен, это значение дескриптора.|  
  
 Переопределите эту функцию-член требуется некоторое действие перед выполнением подпрограммы обратного вызова состояние.  
  
> [!NOTE]
>  Обратные вызовы состояние требуется защита состояние потока. При использовании MFC в общей библиотеке, добавьте следующую строку в начало переопределения:  
  
 [!code-cpp[NVC_MFCHtmlHttp №&8;](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]  
  
 Дополнительные сведения об асинхронных операциях см. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="openurl"></a>CInternetSession::OpenURL  
 Вызовите этот член функции для отправки указанный запрос HTTP-сервер и предоставить клиенту возможность указать дополнительные RFC822 MIME или заголовки HTTP, отправляемые вместе с запросом.  
  
```  
CStdioFile* OpenURL(
    LPCTSTR pstrURL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,  
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLength = 0);
```  
  
### <a name="parameters"></a>Параметры  
 *pstrURL*  
 Указатель на имя URL-адреса, с которого начинается чтение. Только URL-адреса, начиная с файлом:, ftp:, gopher:, или http: поддерживаются. **Операторы Assert** Если *pszURL* — **NULL**.  
  
 `dwContext`  
 Определяемые приложением значения, передаваемый с возвращенный дескриптор в функции обратного вызова.  
  
 `dwFlags`  
 Флаги, описывающие способ обработки данного подключения. В разделе **примечания** Дополнительные сведения о допустимых флагов. Ниже перечислены допустимые флаги  
  
- **INTERNET_FLAG_TRANSFER_ASCII** по умолчанию. Переместите файл в виде текста ASCII.  
  
- **INTERNET_FLAG_TRANSFER_BINARY** передачи файла как двоичного файла.  
  
- `INTERNET_FLAG_RELOAD`Получение данных из сети, даже если он кэшируется локально.  
  
- `INTERNET_FLAG_DONT_CACHE`Не следует кэшировать данные локально или в любой шлюзов.  
  
- `INTERNET_FLAG_SECURE`Этот флаг применяется только HTTP-запросы. Он запрашивает безопасное взаимодействие по сети с помощью протокола SSL или использованию PCT.  
  
- **INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT** по возможности повторного использования существующих подключений к серверу для новых запросов, созданных **OpenUrl** вместо создания нового сеанса для каждого запроса на подключение.  
  
- **INTERNET_FLAG_PASSIVE** для FTP-узла. Использует семантику пассивный FTP. Используется с [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) из `OpenURL`.  
  
 `pstrHeaders`  
 Указатель на строку, содержащую заголовки отправку HTTP-сервера.  
  
 *dwHeadersLength*  
 Длина в символах, дополнительные заголовки. Если это значение-1 L и `pstrHeaders` отличен от **NULL**, затем `pstrHeaders` считается равным нулю завершен и вычисляется длина.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор файла для FTP, GOPHER, HTTP и типов файлов в Интернете служб. Возвращает **NULL** Если синтаксический анализ завершилась ошибкой.  
  
 Указатель, `OpenURL` возвращает зависит от *pszURL*в тип службы. В таблице ниже показаны возможные указатели `OpenURL` может возвращать.  
  
|Введите URL-адрес|Returns|  
|--------------|-------------|  
|file://|**CStdioFile\***|  
|http://|**CHttpFile\***|  
|Gopher://|**CGopherFile\***|  
|FTP: / /|**CInternetFile\***|  
  
### <a name="remarks"></a>Примечания  
 Параметр `dwFlags` должен содержать либо **INTERNET_FLAG_TRANSFER_ASCII** или **INTERNET_FLAG_TRANSFER_BINARY**, но не оба. Остальные флаги могут объединяться с помощью битовой операции `OR` оператор ( **|**).  
  
 `OpenURL`, который создает оболочку для функции Win32 **InternetOpenURL**, позволяет только загрузку, получение и чтение данных из Интернет-сервера. `OpenURL`позволяет без обработки файла в удаленном расположении, поэтому для него требуется не [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) объекта.  
  
 Для использования подключения (то есть определенный протокол) функции, такие как запись в файл, необходимо открыть сеанс, затем откройте определенного типа подключения, а затем используют это подключение, чтобы открыть файл в нужном режиме. В разделе `CInternetConnection` Дополнительные сведения о функции каждого подключения.  
  
##  <a name="operator_hinternet"></a>CInternetSession::operator HINTERNET  
 Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернета.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="setcookie"></a>CInternetSession::SetCookie  
 Задает файл cookie для указанного URL-адреса.  
  
```  
static BOOL SetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPCTSTR pstrCookieData);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrUrl`  
 Указатель нулем строку, которая указывает URL-адрес, для которого следует задать файл cookie.  
  
 `pstrCookieName`  
 Указатель на строку, содержащую имя файла cookie.  
  
 `pstrCookieData`  
 Указатель на строку, содержащую фактические строковых данных для связи с URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** в случае успешного выполнения или **FALSE** в противном случае. Чтобы получить код ошибки, вызовите **GetLastError.**  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение сообщения Win32 [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setoption"></a>CInternetSession::SetOption  
 Вызовите эту функцию-член для установки параметров для Интернет-сеанс.  
  
```  
BOOL SetOption(
    DWORD dwOption,  
    LPVOID lpBuffer,  
    DWORD dwBufferLength,  
    DWORD dwFlags = 0);

 
BOOL SetOption(
    DWORD dwOption,  
    DWORD dwValue,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `dwOption`  
 Параметр Интернета. В разделе [флагам](http://msdn.microsoft.com/library/windows/desktop/aa385328) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]список возможных вариантов.  
  
 `lpBuffer`  
 Буфер, содержащий значение параметра.  
  
 *dwBufferLength*  
 Длина `lpBuffer` или размер `dwValue`.  
  
 `dwValue`  
 Объект `DWORD` , содержащий значение параметра.  
  
 `dwFlags`  
 Указывает различные параметры кэширования. По умолчанию используется значение 0. Возможные значения:  
  
- `INTERNET_FLAG_DONT_CACHE`Не следует кэшировать данные локально или на все серверы шлюза.  
  
- `INTERNET_FLAG_OFFLINE`Загрузка операций выполняется через только постоянный кэш. Если элемент не существует в кэше, возвращается соответствующего кода ошибки. Этот флаг может объединяться с битовой `OR` ( **|**) оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если операция выполнена успешно, значение **TRUE** возвращается. Если произошла ошибка, значение **FALSE** возвращается. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)   
 [Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)   
 [Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)

