---
title: Класс CInternetSession | Документы Microsoft
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 648d295af6ca767eb0291f1eb8f0cd172d0717cc
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041114"
---
# <a name="cinternetsession-class"></a>Класс CInternetSession

Создает и инициализирует один или несколько параллельных сеансов Интернета и, при необходимости, описывает подключение к прокси-серверу.

## <a name="syntax"></a>Синтаксис

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Создает объект `CInternetSession`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CInternetSession::Close](#close)|Закрывает подключение к Интернету, при завершении сеанса Интернета.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Устанавливает состояние подпрограммы обратного вызова.|
|[CInternetSession::GetContext](#getcontext)|Закрывает подключение к Интернету, при завершении сеанса Интернета.|
|[CInternetSession::GetCookie](#getcookie)|Возвращает файлы cookie для указанного URL-адреса и всех его родительских URL-адреса.|
|[CInternetSession::GetCookieLength](#getcookielength)|Извлекает переменную, указание длины куки-файла, сохраненного в буфере.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Откроется FTP-сеанс с сервером. Осуществляет вход пользователя.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Открывает gopher-сервер для приложения, которое пытается установить соединение.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Открывает HTTP-сервер для приложения, которое пытается установить соединение.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Обновляет статус операции, когда включен обратный вызов.|
|[CInternetSession::OpenURL](#openurl)|Выполняет синтаксический анализ и открывает URL-адрес.|
|[CInternetSession::SetCookie](#setcookie)|Задает файл cookie для указанного URL-адреса.|
|[CInternetSession::SetOption](#setoption)|Задает параметры для Интернет-сеанс.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Дескриптор текущего сеанса Интернета.|

## <a name="remarks"></a>Примечания

Если подключение к Интернету должна поддерживаться на время выполнения приложения, можно создать `CInternetSession` член класса [CWinApp](../../mfc/reference/cwinapp-class.md).

После установления сеанса Интернета можно вызвать [OpenURL](#openurl). `CInternetSession` разбор URL-адрес можно, вызвав функцию глобального [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Независимо от его типа протокола `CInternetSession` интерпретирует URL-адрес и управляет им автоматически. Он может обрабатывать запросы для локальных файлов с «file://» URL-адрес ресурса. `OpenURL` Возвращает указатель на [CStdioFile](../../mfc/reference/cstdiofile-class.md) объекта, передавая имя он является локальным файлом.

Если его открыть URL-адрес на сервере Интернета с помощью `OpenURL`, можно прочитать сведения из сайта. Если вы хотите выполнять действия с определенной службы (для, например HTTP, FTP или gopher) для файлов, расположенных на сервере, необходимо установить соответствующее соединение с этим сервером. Чтобы открыть определенного типа подключения напрямую к определенной службе, используйте один из следующих функций-членов:

- [GetGopherConnection](#getgopherconnection) открыть подключение к службе gopher.

- [GetHttpConnection](#gethttpconnection) открыть соединение для службы HTTP.

- [GetFtpConnection](#getftpconnection) открыть подключение к службе FTP.

[SetOption](#setoption) позволяет задать параметры запроса в сеанс, например значения времени ожидания, число повторных попыток и т. д.

`CInternetSession` функции-члены [SetCookie](#setcookie), [GetCookie](#getcookie), и [GetCookieLength](#getcookielength) предоставляют средства для управления базой данных файлов cookie Win32, через который поддерживать серверы и сценарии сведения о состоянии о клиентской рабочей станции.

Дополнительные сведения об основных задач программирования Интернета см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md). Общие сведения об использовании классов MFC WinInet см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession` вызывает исключение [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) для типов службы не поддерживается. В настоящее время поддерживаются только следующие типы службы: FTP, HTTP, gopher и файл.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)  
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetsession"></a> CInternetSession::CInternetSession

Эта функция-член вызывается, когда `CInternetSession` создан объект.

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

*pstrAgent*  
Указатель на строку, которая идентифицирует имя приложения или сущности, вызов функций Интернета (например, «Microsoft Интернет-браузер»). Если *pstrAgent* — **NULL** (по умолчанию), платформа вызывает функцию глобального [AfxGetAppName](application-information-and-management.md#afxgetappname), возвращающий символом null строку, содержащую приложения имя. Некоторые протоколы использовать данную строку для идентификации приложения на сервер.

*dwContext*  
Идентификатор контекста для операции. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](#onstatuscallback). Значение по умолчанию имеет значение 1; Тем не менее можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связана с этим идентификатором контекста.

*dwAccessType*  
Тип доступа. Ниже приведены допустимые значения, только один из которых может быть указано.

- `INTERNET_OPEN_TYPE_PRECONFIG` Подключение с использованием предварительно настроенных параметров в реестре. Этот тип доступа устанавливается по умолчанию. Для подключения через прокси, НАСТАЛО задать *dwAccessType* значению; при этом установить реестр соответствующим образом.

- `INTERNET_OPEN_TYPE_DIRECT` Непосредственное подключение к Интернету.

- `INTERNET_OPEN_TYPE_PROXY` Подключаться через прокси-сервер CERN.

Сведения о подключении с помощью различных типов учетных записей-посредников см. в разделе [шагов в обычном клиентском приложении FTP](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*  
Имя основной прокси-сервер CERN Если *dwAccessType* задается как `INTERNET_OPEN_TYPE_PROXY`. Значение по умолчанию — **NULL**.

*pstrProxyBypass*  
Указатель на строку, содержащую необязательный список адресов серверов. Эти адреса могут обходить при использовании прокси-доступа. Если **NULL** значение предоставляется, то список пропускаемых будет считать из реестра. Этот параметр применяется только тогда, когда *dwAccessType* равно `INTERNET_OPEN_TYPE_PROXY`.

*dwFlags*  
Указывает различные параметры кэширования. Значение по умолчанию имеет значение 0. Возможные значения включают:

- `INTERNET_FLAG_DONT_CACHE` Не следует кэшировать данные, локально или серверов шлюза.

- `INTERNET_FLAG_OFFLINE` Загрузка операций удовлетворены через только постоянного кэша. Если элемент не существует в кэше, возвращается соответствующий код ошибки. Этот флаг могут объединяться с битовой операции `OR` ( **&#124;**) оператор.

### <a name="remarks"></a>Примечания

`CInternetSession` Первая функция Интернет вызывается приложением. Он инициализирует внутренние структуры данных и подготавливает к последующим вызовам из приложения.

Если отсутствует подключение к Интернету может быть открыт, `CInternetSession` вызывает [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Пример

Далее приведен пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>  CInternetSession::Close

Вызовите эту функцию-член по завершении приложения с помощью `CInternetSession` объекта.

```cpp
virtual void Close();
```

### <a name="example"></a>Пример

Далее приведен пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>  CInternetSession::EnableStatusCallback

Вызовите эту функцию-член для включения состояния обратного вызова.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*  
Указывает, включен ли обратного вызова. Значение по умолчанию — **TRUE**.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

При обработке обратного вызова состояние, можно указать состояние о ходе выполнения операции (например, разрешения имени, подключение к серверу и т. д) в строке состояния приложения. Отображение состояния операции желательно особенно во время операции долгосрочного.

Так как обратные вызовы происходят во время обработки запроса, как меньше времени обратного вызова для предотвращения снижения пропускную способность сети должна тратить от приложения. Например размещение диалоговое окно с помощью обратного вызова может быть таких длительной операции, что сервер завершает запрос.

Невозможно удалить состояние обратного вызова, при условии, что для любых обратных вызовов, ожидающих выполнения.

Асинхронная обработка всех операций, необходимо создать собственный поток или используют функции WinInet без использования MFC.

## <a name="getcontext"></a>  CInternetSession::GetContext

Вызовите эту функцию-член для получения значения контекста сеанса конкретного приложения.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определяемые приложением контекст идентификатора.

### <a name="remarks"></a>Примечания

[OnStatusCallback](#onstatuscallback) использует возвращаемый идентификатор контекста `GetContext` для уведомления о состоянии конкретного приложения. Например когда пользователь активирует Интернет-запрос, включающий возвращения информации о состоянии, состояние обратного вызова использует идентификатор контекста для отчета о состоянии этого конкретного запроса. Если пользователь активирует два отдельных Интернет запросов, что оба включают возвращения информации о состоянии, `OnStatusCallback` используется для возврата состояния о своих запросах на соответствующие идентификаторы контекста. Таким образом идентификатор контекста используется для всех операций обратного вызова состояние, и она связана с сеансом до окончания сеанса.

Дополнительные сведения об асинхронных операциях см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>  CInternetSession::GetCookie

Эта функция-член реализует поведение функции Win32 [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), как описано в Windows SDK.

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

*pstrUrl*  
Указатель на строку, содержащую URL-адрес.

*pstrCookieName*  
Указатель на строку, содержащую имя файла cookie для получения указанный URL-адрес.

*pstrCookieData*  
В первой перегрузке указатель на строку, содержащую адрес буфера, принимающего данные cookie. Это значение может быть **NULL**. Во второй перегрузке ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект для получения данных файлов cookie.

*dwBufLen*  
Переменная, определяющий размер *pstrCookieData* буфера. Если функция выполняется успешно, помещаемых в буфер, объем данных, копируемых в *pstrCookieData* буфера. Если *pstrCookieData* — **NULL**, этот параметр получает значение, указывающее размер буфера, необходимый для копирования всех данных файлов cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **TRUE** в случае успешного выполнения или **FALSE** в противном случае. Если вызов завершается неудачей, вызывается функция Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) для определения причины ошибки. Применяются следующие значения ошибки:

- `ERROR_NO_MORE_ITEMS` Нет, объекты cookie не указанный URL-адрес и всех его родительских объектов.

- `ERROR_INSUFFICIENT_BUFFER` Значение, переданное в *dwBufLen* недостаточна для копирования всех данных файлов cookie. Значение, возвращаемое в *dwBufLen* требуется получить все данные, размер буфера.

### <a name="remarks"></a>Примечания

Во второй перегрузке MFC извлекает данные cookie в предоставленном `CString` объекта.

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

Вызовите эту функцию-член получить длину куки-файла, сохраненного в буфере.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Параметры

*pstrUrl*  
Указатель на строку, содержащую URL-адрес

*pstrCookieName*  
Указатель на строку, содержащую имя файла cookie.

### <a name="return-value"></a>Возвращаемое значение

Объект `DWORD` значение, указывающее длину файла cookie, сохраненного в буфере. Нуль, если нет куки-файл с именем, обозначенном *pstrCookieName* существует.

### <a name="remarks"></a>Примечания

Это значение используется [GetCookie](#getcookie).

## <a name="getftpconnection"></a>  CInternetSession::GetFtpConnection

Вызовите эту функцию-член для установки FTP-соединение и получить указатель на `CFtpConnection` объект.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Параметры

*pstrServer*  
Указатель на строку, содержащую имя FTP-сервера.

*pstrUserName*  
Указатель на строку с завершающим нулем, указывающее имя пользователя для входа. Если **NULL**, значение по умолчанию является анонимным.

*pstrPassword*  
Указатель символом null строку, которая указывает пароль, используемый для входа. Если оба *pstrPassword* и *pstrUserName* , **NULL**, анонимных паролей по умолчанию является имя электронной почты пользователя. Если *pstrPassword* — **NULL** (или пустую строку), но *pstrUserName* не **NULL**, используется пустой пароль. В следующей таблице описаны поведение для четыре возможные параметры *pstrUserName* и *pstrPassword*:

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправленных FTP-сервер|Пароль, отправленных FTP-сервер|
|--------------------|--------------------|---------------------------------|---------------------------------|
|**Значение NULL** или «»|**Значение NULL** или «»|«anonymous»|Имя электронной почты пользователя|
|Не-**NULL** строки|**Значение NULL** или «»|*pstrUserName*|" "|
|**NULL**|Не-**NULL** строки|**ОШИБКА**|**ОШИБКА**||
|Не-**NULL** строки|Не-**NULL** строки|*pstrUserName*|*pstrPassword*|

*nPort*  
Число, определяющее порт TCP/IP, используемый на сервере.

*bPassive*  
Задает пассивный или активный режим для этого сеанса FTP. Если значение **TRUE**, он задает Win32 API `dwFlag` для `INTERNET_FLAG_PASSIVE`.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [классе CFtpConnection](../../mfc/reference/cftpconnection-class.md) объекта. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetFtpConnection` подключается к FTP-серверу и создает и возвращает указатель на `CFTPConnection` объект. Он не выполняет любой конкретной операции на сервере. Если вы планируете считывать или записывать файлы, например, необходимо выполнить эти операции как отдельные шаги. В разделе классы [классе CFtpConnection](../../mfc/reference/cftpconnection-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач FTP-соединений.

### <a name="example"></a>Пример

Далее приведен пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>  CInternetSession::GetGopherConnection

Вызовите эту функцию-член для создания нового подключения gopher и получить указатель на `CGopherConnection` объект.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pstrServer*  
Указатель на строку, содержащую имя сервера gopher.

*pstrUserName*  
Указатель на строку, содержащую имя пользователя.

*pstrPassword*  
Указатель на строку, содержащую пароль доступа.

*nPort*  
Число, определяющее порт TCP/IP, используемый на сервере.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) объекта. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetGopherConnection` подключается к серверу gopher и создает и возвращает указатель на `CGopherConnection` объект. Он не выполняет любой конкретной операции на сервере. Если вы собираетесь чтения или записи данных, например, необходимо выполнить эти операции как отдельные шаги. В разделе классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), и [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) сведения о поиске файлов, открытие файлов, чтение и запись в файлы. Сведения о просмотре FTP-сайта см. в разделе функция-член [OpenURL](#openurl). См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач подключения gopher.

## <a name="gethttpconnection"></a>  CInternetSession::GetHttpConnection

Вызовите эту функцию-член для установки соединения HTTP и получить указатель на `CHttpConnection` объект.

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

*pstrServer*  
Указатель на строку, содержащую имя сервера HTTP.

*nPort*  
Число, определяющее порт TCP/IP, используемый на сервере.

*pstrUserName*  
Указатель на строку, содержащую имя пользователя.

*pstrPassword*  
Указатель на строку, содержащую пароль доступа.

*dwFlags*  
Любое сочетание `INTERNET_FLAG_*` флаги. См. в таблице **примечания** раздел [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) описание *dwFlags* значения.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

`GetHttpConnection` подключается к HTTP-сервера и создает и возвращает указатель на `CHttpConnection` объект. Он не выполняет любой конкретной операции на сервере. Если требуется запросить заголовка HTTP, например, необходимо выполнить эту операцию как отдельный шаг. В разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) сведения об операциях, можно выполнить с помощью подключения к HTTP-серверу. Сведения о просмотре на HTTP-сайте см. в разделе функция-член [OpenURL](#openurl). См. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md) за инструкциями по выполнению типовых задач подключение HTTP.

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

*dwContext*  
Значение контекста, предоставляемой приложением.

*dwInternetStatus*  
Код состояния, которое указывает, почему был выполнен обратный вызов. В разделе **примечания** таблицу возможных значений.

*lpvStatusInformation*  
Указатель на буфер, содержащий информацию, необходимую для этого обратного вызова.

*dwStatusInformationLength*  
Размер *lpvStatusInformation*.

### <a name="remarks"></a>Примечания

Необходимо сначала вызвать [EnableStatusCallback](#enablestatuscallback) преимуществами состояние обратного вызова.

*DwInternetStatus* параметр указывает, что операция выполняется и определяет, какое содержимое *lpvStatusInformation* будет. *dwStatusInformationLength* указывает длину данных, содержащихся в *lpvStatusInformation*. Значения состояния *dwInternetStatus* определяется следующим образом:

|Значение|Значение|
|-----------|-------------|
|`INTERNET_STATUS_RESOLVING_NAME`|Поиск IP-адрес с именем, содержащимся в *lpvStatusInformation*.|
|`INTERNET_STATUS_NAME_RESOLVED`|Успешно найден IP-адрес с именем, содержащимся в *lpvStatusInformation*.|
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Подключение к адреса сокета ([SOCKADDR](../../mfc/reference/sockaddr-structure.md)), на который указывает *lpvStatusInformation*.|
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Успешное подключение к адреса сокета (`SOCKADDR`), на который указывает *lpvStatusInformation*.|
|`INTERNET_STATUS_SENDING_REQUEST`|Отправка запроса сведения на сервер. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_ REQUEST_SENT`|Успешно отправлен запрос на сведения о сервере. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_RECEIVING_RESPONSE`|Ожидание ответа на запрос сервера. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Успешно получил ответ от сервера. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_CLOSING_CONNECTION`|Закрывает подключение к серверу. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_CONNECTION_CLOSED`|Успешно завершил подключение к серверу. *LpvStatusInformation* параметр **NULL**.|
|`INTERNET_STATUS_HANDLE_CREATED`|Используемые функции Win32 API [InternetConnect](http://msdn.microsoft.com/library/windows/desktop/aa384363) для указания, что он создан новый маркер. Это позволяет функции вызова Win32 приложения [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) из другого потока, если подключение выполняется слишком долго. Дополнительные сведения об этих функциях см Windows SDKfor.|
|`INTERNET_STATUS_HANDLE_CLOSING`|Успешно завершен, это значение дескриптора.|

Переопределите эту функцию-член требуется какое-либо действие перед выполнением процедуры обратного вызова состояние.

> [!NOTE]
> Обратные вызовы состояние требуется защита состояние потока. Если вы используете MFC в общей библиотеке, добавьте следующую строку в начало переопределения:

 [!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Дополнительные сведения об асинхронных операциях см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>  CInternetSession::OpenURL

Этот член способ вызова функции для отправки указанного запроса HTTP-сервера и предоставить клиенту возможность указать дополнительные RFC822 MIME или заголовки HTTP для отправки вместе с запросом.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Параметры

*pstrURL*  
Указатель на имя URL-адрес начинается чтение. Только URL-адреса, начиная с файлом:, ftp:, gopher:, или http: поддерживаются. Утверждает, если *pstrURL* — **NULL**.

*dwContext*  
Определяемые приложением значения, переданного с возвращаемый дескриптор при обратном вызове.

*dwFlags*  
Флаги, описывающие способ обработки этого подключения. В разделе **примечания** Дополнительные сведения о Допустимые флаги. Ниже приведены допустимые флаги.

- `INTERNET_FLAG_TRANSFER_ASCII` Значение по умолчанию. Переместите файл в виде текста ASCII.

- `INTERNET_FLAG_TRANSFER_BINARY` Переместите файл в двоичном формате.

- `INTERNET_FLAG_RELOAD` Получите данные из проводной сети, даже если он кэшируется локально.

- `INTERNET_FLAG_DONT_CACHE` Не следует кэшировать данные, локально или в всех шлюзов.

- `INTERNET_FLAG_SECURE` Этот флаг применим только для HTTP-запросов. Он запрашивает защиты транзакций в сети с помощью протокола SSL или использованию PCT.

- `INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT` Если это возможно, повторно использовать существующие подключения к серверу для новых запросов, созданные `OpenUrl` вместо создания нового сеанса для каждого запроса на подключение.

- `INTERNET_FLAG_PASSIVE` Используется для FTP-сайта. Использует семантику пассивный FTP. При использовании [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) из `OpenURL`.

*pstrHeaders*  
Указатель на строку, содержащую заголовки, отправляемую на сервер HTTP.

*dwHeadersLength*  
Длина в символах, дополнительных заголовков. Если это значение-1 L и *pstrHeaders* не является**NULL**, затем *pstrHeaders* предполагается равным нулю завершен и вычисляется длина.

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор файла для FTP, GOPHER, HTTP и тип файла Internet services. Возвращает **NULL** при синтаксическом анализе завершилась неудачно.

Указатель, `OpenURL` зависит от возвращает *pstrURL*в тип службы. В таблице ниже рассмотрены возможные указатели `OpenURL` может возвращать.

|Тип URL-адреса|Returns|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|Gopher://|`CGopherFile*`|
|FTP: / /|`CInternetFile*`|

### <a name="remarks"></a>Примечания

Параметр *dwFlags* необходимо включить `INTERNET_FLAG_TRANSFER_ASCII` или `INTERNET_FLAG_TRANSFER_BINARY`, но не оба. Остальные флаги могут объединяться с помощью битовой операции `OR` оператор ( **&#124;**).

`OpenURL`, который создает оболочку для функции Win32 `InternetOpenURL`, позволяет только загрузки, извлечения и чтение данных из веб-сервером. `OpenURL` позволяет не обработке файла в удаленном расположении, поэтому для него требуется нет [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) объекта.

Для использования подключения (то есть протоколом) функции, такие как запись в файл, необходимо открыть сеанс, затем откройте конкретный тип соединения, и используют это подключение, чтобы открыть файл в нужном режиме. В разделе `CInternetConnection` Дополнительные сведения о функции, зависящие от подключения.

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

Этот оператор используется для получения дескриптора Windows для текущего сеанса Интернета.

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

*pstrUrl*  
Указатель символом null строку, которая указывает URL-адрес, для которого следует задать куки-файл.

*pstrCookieName*  
Указатель на строку, содержащую имя файла cookie.

*pstrCookieData*  
Указатель на строку, содержащую фактические строковых данных для связи с URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает **TRUE** в случае успешного выполнения или **FALSE** в противном случае. Чтобы получить код ошибки, вызовите **GetLastError.**

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщения Win32 [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), как описано в Windows SDK.

## <a name="setoption"></a>  CInternetSession::SetOption

Вызовите эту функцию-член для задания параметров для Интернет-сеанс.

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

*dwOption*  
Параметр Интернета. В разделе [флагам](http://msdn.microsoft.com/library/windows/desktop/aa385328) в Windows SDKfor список возможных вариантов.

*lpBuffer*  
Буфер, содержащий значение параметра.

*dwBufferLength*  
Длина *lpBuffer* или размер *dwValue*.

*dwValue*  
Объект `DWORD` , содержащий значение параметра.

*dwFlags*  
Указывает различные параметры кэширования. Значение по умолчанию имеет значение 0. Возможные значения включают:

- `INTERNET_FLAG_DONT_CACHE` Не следует кэшировать данные, локально или серверов шлюза.

- `INTERNET_FLAG_OFFLINE` Загрузка операций удовлетворены через только постоянного кэша. Если элемент не существует в кэше, возвращается соответствующий код ошибки. Этот флаг могут объединяться с битовой операции `OR` ( **&#124;**) оператор.

### <a name="return-value"></a>Возвращаемое значение

Если операция выполнена успешно, значение **TRUE** возвращается. Если произошла ошибка, значение **FALSE** возвращается. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)  
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)  
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)  
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)  
[Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)  
