---
title: Класс CInternetSession
ms.date: 06/20/2018
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
helpviewer_keywords:
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
ms.openlocfilehash: 3b820ea3687fd52947eff48e4814ab4173fd95c7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519297"
---
# <a name="cinternetsession-class"></a>Класс CInternetSession

Создает и инициализирует один или несколько параллельных сеансов Интернета и, при необходимости, описывает подключение к прокси-серверу.

## <a name="syntax"></a>Синтаксис

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Создает объект `CInternetSession`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession::Close](#close)|Закрывает подключение к Интернету, при завершении сеанса Интернет.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Устанавливает программу ответного вызова состояние.|
|[CInternetSession::GetContext](#getcontext)|Закрывает подключение к Интернету, при завершении сеанса Интернет.|
|[CInternetSession::GetCookie](#getcookie)|Возвращает файлы cookie для указанного URL-адрес и всех его родительских URL-адреса.|
|[CInternetSession::GetCookieLength](#getcookielength)|Извлекает переменную, задающее длину файла cookie, сохраненного в буфере.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Откроется сеанс FTP с сервером. Выполняет вход в систему.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Открывает gopher-сервер для приложения, которое пытается установить соединение.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Откроется сервер HTTP для приложения, которое пытается установить соединение.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Обновляет состояние операции, когда включен обратный вызов.|
|[CInternetSession::OpenURL](#openurl)|Выполняет синтаксический анализ и открывает URL-адрес.|
|[CInternetSession::SetCookie](#setcookie)|Задает файл cookie для указанного URL-адреса.|
|[CInternetSession::SetOption](#setoption)|Задает параметры для Интернет-сеанс.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Дескриптор текущего сеанса Интернет.|

## <a name="remarks"></a>Примечания

Если в течение приложения нужно поддерживать подключение к Интернету, вы можете создать `CInternetSession` член класса [CWinApp](../../mfc/reference/cwinapp-class.md).

После установки Интернета, можно вызвать [OpenURL](#openurl). `CInternetSession` затем анализирует URL-адрес для вас, вызвав функцию глобального [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Независимо от его типа протокола `CInternetSession` интерпретирует URL-адрес и управляет им автоматически. Он может обрабатывать запросы для локальных файлов, идентифицируемое ресурс URL-адреса «file://». `OpenURL` Возвращает указатель на [CStdioFile](../../mfc/reference/cstdiofile-class.md) объекта, если имя его передавать представляет собой локальный файл.

Если открыть URL-адрес на сервере Интернета с помощью `OpenURL`, может считывать сведения из сайта. Если вы хотите выполнять действия конкретной службы (для, например HTTP, FTP или gopher) в файлах, расположенных на сервере, необходимо установить соответствующее соединение с этим сервером. Чтобы открыть конкретный вид подключения непосредственно к конкретной службе, используйте один из следующих функций-членов:

- [GetGopherConnection](#getgopherconnection) открыть подключение к службе gopher.

- [GetHttpConnection](#gethttpconnection) открыть подключение к HTTP-службу.

- [GetFtpConnection](#getftpconnection) открыть подключение к службе FTP.

[SetOption](#setoption) позволяет задать параметры запроса в сеанс, таких как значения времени ожидания, число повторных попыток и т. д.

`CInternetSession` функции-члены [SetCookie](#setcookie), [GetCookie](#getcookie), и [GetCookieLength](#getcookielength) предоставляют средства для управления базой данных файлов cookie Win32, через который поддерживать серверы и сценарии сведения о состоянии о клиентской рабочей станции.

Дополнительные сведения об основных задачах программирования Интернета см. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md). Общие сведения об использовании классов MFC WinInet см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession` вызывает исключение [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) для типов службы не поддерживается. В настоящее время поддерживаются только следующих типов служб: FTP, HTTP, gopher и файл.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetsession"></a> CInternetSession::CInternetSession

Эта функция-член вызывается, когда `CInternetSession` создается объект.

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*pstrAgent*<br/>
Указатель на строку, которая идентифицирует имя приложения или сущность, вызвав Интернет-функции (например, «Microsoft Интернет-браузер»). Если *pstrAgent* имеет значение NULL (по умолчанию), платформа вызывает функцию глобального [AfxGetAppName](application-information-and-management.md#afxgetappname), который возвращает заканчивающуюся нулем строку, содержащую имя приложения. Некоторые протоколы использовать эту строку для идентификации приложения на сервер.

*dwContext*<br/>
Идентификатор контекста для операции. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](#onstatuscallback). Значение по умолчанию имеет значение 1; Тем не менее можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связан с этим идентификатором контекста.

*dwAccessType*<br/>
Тип необходимый доступ. Ниже приведены допустимые значения, только один из которых может быть предоставлен.

- INTERNET_OPEN_TYPE_PRECONFIG соединиться при помощи заранее настроенные параметры в реестре. Этот тип доступа имеет значение по умолчанию. Чтобы подключаться через прокси-сервер еще ПРИВЛЕКАТЕЛЬНЕЕ, задайте *dwAccessType* этому значению; при этом установить реестра соответствующим образом.

- INTERNET_OPEN_TYPE_DIRECT подключиться непосредственно к Интернету.

- INTERNET_OPEN_TYPE_PROXY подключаться через прокси-сервер CERN.

Дополнительные сведения о подключении с разными типами учетных записей-посредников, см. в разделе [шагов в обычном клиентском приложении FTP](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*<br/>
Имя предпочтительной прокси CERN Если *dwAccessType* задается как INTERNET_OPEN_TYPE_PROXY. Значение по умолчанию имеет значение NULL.

*pstrProxyBypass*<br/>
Указатель на строку, содержащую необязательный список адресов серверов. Эти адреса могут быть обойдены, при использовании прокси-доступа. Если задано значение NULL, в списке пропускаемых адресов будет считывать из реестра. Этот параметр имеет смысл только если *dwAccessType* присваивается INTERNET_OPEN_TYPE_PROXY.

*dwFlags*<br/>
Указывает различные параметры кэширования. Значение по умолчанию имеет значение 0. Возможные значения включают:

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, локально или в любой серверов шлюзов.

- Скачайте INTERNET_FLAG_OFFLINE операции выполняются через постоянный кэш только. Если элемент не существует в кэше, соответствующего кода ошибки возвращается. Этот флаг можно использовать совместно с побитовым **или** ( **&#124;**) оператор.

### <a name="remarks"></a>Примечания

`CInternetSession` Первая функция Internet, вызывается приложением. Он инициализирует внутренние структуры данных и подготавливает для последующих вызовов из приложения.

Если нет подключения к Интернету может быть открыт, `CInternetSession` вызывает [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Пример

См. в примере [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>  CInternetSession::Close

Вызовите эту функцию-член, когда приложение завершило использование `CInternetSession` объекта.

```cpp
virtual void Close();
```

### <a name="example"></a>Пример

См. в примере [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>  CInternetSession::EnableStatusCallback

Вызовите эта функция-член для включения обратного вызова состояния.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Указывает, включена ли обратного вызова. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

При обработке обратного вызова состояние, можно указать состояние о ходе выполнения операции (например, разрешение имени, подключение к серверу и т. д.) в строке состояния приложения. Отображение состояния операции желательно особенно во время долгосрочной операции.

Так как обратные вызовы происходят во время обработки запроса, приложения следует тратить как меньше времени в обратном вызове для предотвращения снижения пропускной способности данных к сети. Например поместив откроется диалоговое окно, в обратном вызове может быть такой длительной операции, что сервер завершает запрос.

Обратный вызов состояния нельзя удалить до тех пор, пока все обратных вызовов, ожидающих выполнения.

Для обработки всех операций в асинхронном режиме, необходимо создать собственный поток или использовать функции WinInet без использования MFC.

## <a name="getcontext"></a>  CInternetSession::GetContext

Вызов этой функции-члена для получения значения контекста сеанса конкретного приложения.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определяемый приложением контекст идентификатора.

### <a name="remarks"></a>Примечания

[OnStatusCallback](#onstatuscallback) использует идентификатор контекста возвращается `GetContext` для уведомления о состоянии конкретного приложения. Например когда пользователь активирует Интернет-запрос, который включает в себя возвращения информации о состоянии, обратный вызов состояния использует идентификатор контекста для отчета о состоянии на этого конкретного запроса. Если пользователь активирует два отдельных Internet запросов, что в обоих случаях используются возвращения информации о состоянии, `OnStatusCallback` используется для возврата состояния о своих запросах соответствующие идентификаторы контекстов управляются объектами. Следовательно идентификатор контекста используется для всех операций обратного вызова состояния, и она связана с сеансом до окончания сеанса.

Дополнительные сведения об асинхронных операциях см. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>  CInternetSession::GetCookie

Эта функция-член реализует поведение функции Win32 [InternetGetCookie](/windows/desktop/api/wininet/nf-wininet-internetgetcookiea), как описано в пакете Windows SDK.

```cpp
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

*pstrUrl*<br/>
Указатель на строку, содержащую URL-адрес.

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie, чтобы получить для указанного URL-адрес.

*pstrCookieData*<br/>
В первой перегрузке указатель на строку, содержащую адрес буфера, который получает данные файла cookie. Это значение может быть NULL. Во второй перегрузке, ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект для получения данных файлов cookie.

*dwBufLen*<br/>
Переменная, указывая размер *pstrCookieData* буфера. Если функция выполняется успешно, помещаемых в буфер, объем данных, копируемых в *pstrCookieData* буфера. Если *pstrCookieData* имеет значение NULL, этот параметр получает значение, указывающее размер буфера, необходимый для копирования всех данных файлов cookie.

### <a name="return-value"></a>Возвращаемое значение

В противном случае возвращает значение TRUE, если успешно, или значение FALSE. Если вызов завершается неудачно, вызывается функция Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) для определения причины ошибки. Применяются следующие значения ошибок:

- ERROR_NO_MORE_ITEMS имеется cookie не для указанного URL-адреса и все его родительские элементы.

- Значение, переданное значение ERROR_INSUFFICIENT_BUFFER *dwBufLen* не позволяет скопировать все данные файла cookie. Значение, возвращаемое в *dwBufLen* — это размер буфера для получения всех данных.

### <a name="remarks"></a>Примечания

Во второй перегрузке MFC извлекает данные файла cookie в предоставленный `CString` объекта.

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

Вызов для получения длины файла cookie, сохраненные в буфере, эта функция-член.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Параметры

*pstrUrl*<br/>
Указатель на строку, содержащую URL-адрес

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, указывающее длину файла cookie, сохраненного в буфере. Нуль, если нет файл cookie с именем обозначается *pstrCookieName* существует.

### <a name="remarks"></a>Примечания

Это значение используется по [GetCookie](#getcookie).

## <a name="getftpconnection"></a>  CInternetSession::GetFtpConnection

Вызывайте эту функцию члена, чтобы подключиться к FTP и получить указатель на `CFtpConnection` объект.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Параметры

*pstrServer*<br/>
Указатель на строку, содержащую имя FTP-сервера.

*pstrUserName*<br/>
Указатель на заканчивающуюся нулем строку, указывающее имя пользователя для входа. Если значение равно NULL, значение по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на заканчивающуюся нулем строку, указывающее пароль, используемый для входа. Если оба *pstrPassword* и *pstrUserName* имеют значение NULL, анонимные пароль по умолчанию — имя электронной почты пользователя. Если *pstrPassword* имеет значение NULL (или пустую строку), но *pstrUserName* не равно NULL, используется пустой пароль. В следующей таблице описаны поведение четыре возможные параметры *pstrUserName* и *pstrPassword*:

| *pstrUserName*  | *pstrPassword*  | Имя пользователя, отправляемые серверу FTP | Пароля, передаваемых на FTP-сервер |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   Значение NULL или ""   |   Значение NULL или ""   |         «anonymous»         |      Имя электронной почты пользователя      |
| НЕНУЛЕВЫЕ строковые |   Значение NULL или ""   |       *pstrUserName*        |             " "             |
|      NULL       | НЕНУЛЕВЫЕ строковые |            ОШИБКА            |            ОШИБКА            |
| НЕНУЛЕВЫЕ строковые | НЕНУЛЕВЫЕ строковые |       *pstrUserName*        |       *pstrPassword*        |

*nPort*<br/>
Число, идентифицирующее порт TCP/IP, используемый на сервере.

*bPassive*<br/>
Задает пассивный или активный режим для этого сеанса FTP. Если задано значение TRUE, то он устанавливает Win32 API `dwFlag` для INTERNET_FLAG_PASSIVE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CFtpConnection](../../mfc/reference/cftpconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetFtpConnection` подключается к FTP-сервера и создает и возвращает указатель на `CFTPConnection` объект. Он не выполняет любой конкретной операции на сервере. Если вы планируете считывать или записывать файлы, например, необходимо выполнить эти операции отдельно. См. в разделе классы [CFtpConnection](../../mfc/reference/cftpconnection-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. См. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) для выполнения действий в выполнение типичных задач подключения FTP.

### <a name="example"></a>Пример

См. в примере [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>  CInternetSession::GetGopherConnection

Вызывайте эту функцию члена, чтобы установить новое подключение gopher и получить указатель на `CGopherConnection` объект.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера gopher.

*pstrUserName*<br/>
Указатель на строку, содержащую имя пользователя.

*pstrPassword*<br/>
Указатель на строку, содержащую пароль доступа.

*nPort*<br/>
Число, идентифицирующее порт TCP/IP, используемый на сервере.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetGopherConnection` подключается к серверу gopher и создает и возвращает указатель на `CGopherConnection` объект. Он не выполняет любой конкретной операции на сервере. Если вы собираетесь чтения или записи данных, например, необходимо выполнить эти операции отдельно. См. в разделе классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), и [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. Сведения о просмотре FTP-сайта, см. в разделе функция-член [OpenURL](#openurl). См. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) для выполнения действий в выполнение типичных задач подключения gopher.

## <a name="gethttpconnection"></a>  CInternetSession::GetHttpConnection

Вызов этой функции-члена для установки соединения HTTP и получить указатель на `CHttpConnection` объект.

```cpp
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

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера HTTP.

*nPort*<br/>
Число, идентифицирующее порт TCP/IP, используемый на сервере.

*pstrUserName*<br/>
Указатель на строку, содержащую имя пользователя.

*pstrPassword*<br/>
Указатель на строку, содержащую пароль доступа.

*dwFlags*<br/>
Любое сочетание `INTERNET_FLAG_*` флаги. См. в таблице в **"Примечания"** раздел [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) описание *dwFlags* значения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetHttpConnection` подключается к серверу HTTP и создает и возвращает указатель на `CHttpConnection` объект. Он не выполняет любой конкретной операции на сервере. Например, если запросить заголовок HTTP, необходимо выполнить эту операцию как отдельный шаг. См. в разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) для сведения об операциях, которые можно выполнить с помощью подключения к серверу HTTP. Сведения о просмотре на HTTP-сайте см. в разделе функция-член [OpenURL](#openurl). См. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) для выполнения действий в выполнении обычных задач подключения HTTP.

## <a name="onstatuscallback"></a>  CInternetSession::OnStatusCallback

Эта функция-член вызывается платформой для обновления состояния, когда включен обратный вызов, и операция находится в состоянии ожидания.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Параметры

*dwContext*<br/>
Значение контекста приложения.

*dwInternetStatus*<br/>
Код состояния, указывающий причину обратного вызова. См. в разделе **"Примечания"** таблицу возможных значений.

*lpvStatusInformation*<br/>
Указатель на буфер, содержащий сведения, относящиеся к этой функции обратного вызова.

*dwStatusInformationLength*<br/>
Размер *lpvStatusInformation*.

### <a name="remarks"></a>Примечания

Сначала необходимо вызвать [EnableStatusCallback](#enablestatuscallback) преимуществами состояние обратного вызова.

*DwInternetStatus* параметр указывает, выполняемой операции и определяет, какое содержимое *lpvStatusInformation* будет. *dwStatusInformationLength* указывает длину данных, включенных в *lpvStatusInformation*. Значения для следующих состояния *dwInternetStatus* определяются следующим образом:

|Значение|Значение|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|Поиск IP-адрес с именем, содержащимся в *lpvStatusInformation*.|
|INTERNET_STATUS_NAME_RESOLVED|Успешно найден IP-адрес с именем, содержащимся в *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Подключение к адреса сокета ([SOCKADDR](../../mfc/reference/sockaddr-structure.md)), на которые указывают *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|Успешно подключились к адреса сокета (SOCKADDR), на которые указывают *lpvStatusInformation*.|
|INTERNET_STATUS_SENDING_REQUEST|Отправляет запрос информации на сервер. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_ REQUEST_SENT|Успешно отправлен запрос информации на сервер. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Ожидание ответа на запрос сервера. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Успешно получил ответ от сервера. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_CLOSING_CONNECTION|Закрытие подключения к серверу. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_CONNECTION_CLOSED|Успешно закрыл подключение к серверу. *LpvStatusInformation* параметр имеет значение NULL.|
|INTERNET_STATUS_HANDLE_CREATED|Функция Win32 API [InternetConnect](/windows/desktop/api/wininet/nf-wininet-internetconnecta) для указания, что он создан новый маркер. Это позволяет функции вызова Win32 приложения [InternetCloseHandle](/windows/desktop/api/wininet/nf-wininet-internetclosehandle) из другого потока, если подключение выполняется слишком долго. Дополнительные сведения об этих функциях см. Windows SDKfor.|
|INTERNET_STATUS_HANDLE_CLOSING|Успешно завершены, это значение дескриптора.|

Переопределите эту функцию-член требуется какое-либо действие, прежде чем будет выполнено подпрограммы обратного вызова состояния.

> [!NOTE]
> Обратные вызовы состояние нуждаются в защите состояние потока. Если вы используете MFC в общей библиотеке, добавьте следующую строку в начало переопределение:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Дополнительные сведения об асинхронных операциях см. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>  CInternetSession::OpenURL

Вызовите этот член функции для отправки указанного запроса HTTP-сервера и предоставить клиенту возможность указать дополнительные RFC822 MIME или заголовки HTTP для отправки вместе с запросом.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Параметры

*pstrURL*<br/>
Указатель на имя URL-адрес начинается чтение. Только URL-адреса начиная с файлом:, ftp:, gopher:, или http: поддерживаются. Утверждает, если *pstrURL* имеет значение NULL.

*dwContext*<br/>
Возвращенный дескриптор в функции обратного вызова передается значение, определенное приложением.

*dwFlags*<br/>
Флаги, описывающие способ обработки этого подключения. См. в разделе **"Примечания"** Дополнительные сведения о Допустимые флаги. Ниже приведены допустимые флаги.

- INTERNET_FLAG_TRANSFER_ASCII по умолчанию. Переместите файл в виде текста ASCII.

- INTERNET_FLAG_TRANSFER_BINARY передать файл как двоичный файл.

- INTERNET_FLAG_RELOAD получение данных из сети, даже если он кэшируется локально.

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, локально или в всех шлюзов.

- Этот флаг INTERNET_FLAG_SECURE применим только запросы HTTP. Он запрашивает безопасные транзакции по сети с помощью Secure Sockets Layer или использованию PCT.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT Если это возможно, повторно использовать существующие подключения к серверу для новых запросов, создаваемых `OpenUrl` вместо создания нового сеанса для каждого запроса подключения.

- INTERNET_FLAG_PASSIVE используется для FTP-сайта. Использует семантику пассивный FTP. Используется с [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) из `OpenURL`.

*pstrHeaders*<br/>
Указатель на строку, содержащую заголовки отправку HTTP-сервера.

*dwHeadersLength*<br/>
Длина в символах, дополнительных заголовков. Если это значение-1 L и *pstrHeaders* не равно NULL, затем *pstrHeaders* предполагается, что должно быть равно нулю завершается и вычисляется длина.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор файла, для FTP, GOPHER, HTTP и типов файлов в Интернете служб. Возвращает значение NULL, если синтаксический анализ выполнен неудачно.

Указатель, `OpenURL` зависит от возвращает *pstrURL*тип службы. В таблице ниже показаны возможные указатели `OpenURL` может возвращать.

|Тип URL-адреса|Returns|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|Gopher://|`CGopherFile*`|
|FTP: / /|`CInternetFile*`|

### <a name="remarks"></a>Примечания

Параметр *dwFlags* должен включать INTERNET_FLAG_TRANSFER_ASCII или INTERNET_FLAG_TRANSFER_BINARY, но не оба. Остальные флаги можно объединить с помощью побитовой операции **или** оператор ( **&#124;**).

`OpenURL`, который создает оболочку для функции Win32 `InternetOpenURL`, позволяет только загрузка, получение и считывание данных с сервера в Интернете. `OpenURL` позволяет не файлами в удаленном расположении, поэтому он не требует [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) объекта.

Использовать зависящий от подключения (то есть, относящиеся к протоколу) функции, такие как запись в файл, необходимо открыть сеанс, затем откройте определенного типа подключения, а затем используйте это подключение, чтобы открыть файл в нужном режиме. См. в разделе `CInternetConnection` Дополнительные сведения о функциях зависящий от подключения.

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернет.

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>  CInternetSession::SetCookie

Задает файл cookie для указанного URL-адреса.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Параметры

*pstrUrl*<br/>
Указатель на заканчивающуюся нулем строку, которая указывает URL-адрес, для которого задается файл cookie.

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie.

*pstrCookieData*<br/>
Указатель на строку, содержащую фактические данные, связать с URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

В противном случае возвращает значение TRUE, если успешно, или значение FALSE. Чтобы получить конкретный код ошибки, вызовите `GetLastError.`

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщение Win32 [InternetSetCookie](/windows/desktop/api/wininet/nf-wininet-internetsetcookiea), как описано в пакете Windows SDK.

## <a name="setoption"></a>  CInternetSession::SetOption

Вызывайте эту функцию члена, чтобы задать параметры для сеанса Internet.

```cpp
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

*dwOption*<br/>
Параметр Internet. См. в разделе [флаги параметров](/windows/desktop/WinInet/option-flags) в Windows SDKfor список возможных вариантов.

*lpBuffer*<br/>
Буфер, содержащий значение параметра.

*dwBufferLength*<br/>
Длина *lpBuffer* или размер *dwValue*.

*dwValue*<br/>
DWORD, содержащее значение параметра.

*dwFlags*<br/>
Указывает различные параметры кэширования. Значение по умолчанию имеет значение 0. Возможные значения включают:

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, локально или в любой серверов шлюзов.

- Скачайте INTERNET_FLAG_OFFLINE операции выполняются через постоянный кэш только. Если элемент не существует в кэше, соответствующего кода ошибки возвращается. Этот флаг можно использовать совместно с побитовым **или** ( **&#124;**) оператор.

### <a name="return-value"></a>Возвращаемое значение

Если операция выполнена успешно, возвращается значение TRUE. Если произошла ошибка, возвращается значение FALSE. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)<br/>
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)<br/>
[Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)
