---
title: Класс CHttpFile
ms.date: 11/04/2016
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
ms.openlocfilehash: 3ee92a6cb627cee701b9b98a8a32666a0877f62c
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893656"
---
# <a name="chttpfile-class"></a>Класс CHttpFile

Предоставляет функции для запроса и чтения файлов на HTTP-сервере.

## <a name="syntax"></a>Синтаксис

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|Создает объект `CHttpFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Добавляет заголовки запроса, отправленного на HTTP-сервер.|
|[CHttpFile::EndRequest](#endrequest)|Завершает запрос, отправленный в HTTP-сервер с [SendRequestEx](#sendrequestex) функция-член.|
|[CHttpFile::GetFileURL](#getfileurl)|Получает URL-адрес для указанного файла.|
|[CHttpFile::GetObject](#getobject)|Возвращает целевой объект команды в запросе на HTTP-сервер.|
|[CHttpFile::GetVerb](#getverb)|Получает команду, которая использовалась в запросе на HTTP-сервер.|
|[CHttpFile::QueryInfo](#queryinfo)|Возвращает заголовки запроса или ответа из HTTP-сервера.|
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Получает код состояния, связанный с HTTP-запрос и помещает его в предоставленном `dwStatusCode` параметра.|
|[CHttpFile::SendRequest](#sendrequest)|Отправляет запрос HTTP-сервера.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Отправляет запрос к серверу HTTP с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) или [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`.|

## <a name="remarks"></a>Примечания

Если сеанс Internet считывает данные из HTTP-сервер, необходимо создать экземпляр `CHttpFile`.

Дополнительные сведения о том, как `CHttpFile` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="addrequestheaders"></a>  CHttpFile::AddRequestHeaders

Вызов этой функции-члена для добавления одного или обрабатывать дополнительные заголовки HTTP-запроса в HTTP-запрос.

```
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,
    int dwHeadersLen = -1);

BOOL AddRequestHeaders(
    CString& str,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```

### <a name="parameters"></a>Параметры

*pstrHeaders*<br/>
Указатель на строку, содержащую заголовок или заголовки для добавления к запросу. Каждый заголовок, должна заканчиваться точкой пару CR/LF.

*dwFlags*<br/>
Изменяет семантику новые заголовки. Ниже указаны доступные значения.

- Выполняет слияние HTTP_ADDREQ_FLAG_COALESCE заголовки с тем же именем, с помощью флага для добавления первого заголовка найдено в последующих заголовок. Например «Accept: текст /\*"следуют «Accept: аудио /\*" приводит к образование одного заголовка «Accept: текст /\*аудио /\*«. Это, вызывающий приложение должно обеспечить единую схему с учетом данных, полученных запросов, отправленных с заголовками совместно или за его пределами.

- HTTP_ADDREQ_FLAG_REPLACE выполняет удаление и добавление для замены текущего заголовка. Имя заголовка, которые будут использоваться для удаления текущего заголовка, а полное значение будет использоваться для добавления нового заголовка. Если значение заголовка является пустым и заголовок найден, он удаляется. В противном случае пустая, значение заголовка заменяется.

- Добавляет заголовок HTTP_ADDREQ_FLAG_ADD_IF_NEW только в том случае, если он еще не существует. Если таковой существует, возвращается ошибка.

- HTTP_ADDREQ_FLAG_ADD используется с функцией REPLACE. Добавляет заголовок, если он не существует.

*dwHeadersLen*<br/>
Длина в символах, из *pstrHeaders*. Если это L-1, затем *pstrHeaders* предполагается, что оканчивающаяся нулем и длина является вычисляемым.

*str*<br/>
Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий заголовок запроса или добавлять заголовки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

`AddRequestHeaders` Добавляет заголовки дополнительные, свободный формат дескриптора запроса HTTP. Он предназначен для использования сложные клиенты, которым необходим подробный контроль над точного запроса, отправленного сервером HTTP.

> [!NOTE]
>  Можно передать несколько заголовков в *pstrHeaders* или *str* для `AddRequestHeaders` вызов с использованием HTTP_ADDREQ_FLAG_ADD или HTTP_ADDREQ_FLAG_ADD_IF_NEW. Если приложение попытается удалить или заменить заголовок, использующий HTTP_ADDREQ_FLAG_REMOVE или HTTP_ADDREQ_FLAG_REPLACE, можно указать только один заголовок в *lpszHeaders*.

##  <a name="chttpfile"></a>  CHttpFile::CHttpFile

Эта функция-член вызывается для создания `CHttpFile` объекта.

```
CHttpFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrObject,
    LPCTSTR pstrServer,
    LPCTSTR pstrVerb,
    DWORD_PTR dwContext);

CHttpFile(
    HINTERNET hFile,
    LPCTSTR pstrVerb,
    LPCTSTR pstrObject,
    CHttpConnection* pConnection);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Дескриптор файла Интернета.

*hSession*<br/>
Дескриптор для Интернет-сеанс.

*pstrObject*<br/>
Указатель на строку, содержащую `CHttpFile` объекта.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*pstrVerb*<br/>
Указатель на строку, содержащую метод, используемый при отправке запроса. Может быть POST, HEAD, или получить.

*dwContext*<br/>
Идентификатор контекста для `CHttpFile` объекта. См. в разделе **"Примечания"** Дополнительные сведения об этом параметре.

*pConnection*<br/>
Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта.

### <a name="remarks"></a>Примечания

Никогда не создавать `CHttpFile` объекта напрямую; вместо этого вызовите [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) вместо этого.

Значение по умолчанию для `dwContext` отправленные MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове `CInternetSession::OpenURL` или `CHttpConnection` для создания `CHttpFile` объекта, можно переопределить значение по умолчанию присвоено значение по своему выбору, идентификатор контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния в объекте, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="endrequest"></a>  CHttpFile::EndRequest

Вызовите эту функцию-член для завершения запроса, отправленного в HTTP-сервер с [SendRequestEx](#sendrequestex) функция-член.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов, см. в разделе [HttpEndRequest](/windows/desktop/api/wininet/nf-wininet-httpendrequesta) в пакете Windows SDK.

*lpBuffIn*<br/>
Указатель на инициализированный [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) , описывающий входной буфер, используемый для операции.

*dwContext*<br/>
Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

Значение по умолчанию для *dwContext* отправленные MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию присвоено значение по своему выбору, идентификатор контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния в объекте, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="getfileurl"></a>  CHttpFile::GetFileURL

Вызывайте эту функцию член, чтобы получить имя файла HTTP в виде URL-адрес.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес, ссылка на ресурс, связанный с этим файлом.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или на `CHttpFile` успешно созданного объектом [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getobject"></a>  CHttpFile::GetObject

Эта функция-член для получения имени объекта, связанного с этим вызывать `CHttpFile`.

```
CString GetObject() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя объекта.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или на `CHttpFile` успешно созданного объектом [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getverb"></a>  CHttpFile::GetVerb

Вызовите эта функция-член для получения HTTP команды (или метода) связанный с этим `CHttpFile`.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя HTTP-команды (или метод).

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или на `CHttpFile` успешно созданного объектом [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="queryinfo"></a>  CHttpFile::QueryInfo

Вызовите эту функцию-член возвращает ответ или заголовки запроса из HTTP-запроса.

```
BOOL QueryInfo(
    DWORD dwInfoLevel,
    LPVOID lpvBuffer,
    LPDWORD lpdwBufferLength,
    LPDWORD lpdwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    CString& str,
    LPDWORD dwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    SYSTEMTIME* pSysTime,
    LPDWORD dwIndex = NULL) const;
```

### <a name="parameters"></a>Параметры

*dwInfoLevel*<br/>
Сочетание атрибута для запросов и следующие флаги, указывающие тип запрашиваемые сведения:

- HTTP_QUERY_CUSTOM находит имя заголовка и возвращает это значение в *lpvBuffer* на выходе. HTTP_QUERY_CUSTOM вызывает проверочное утверждение, если заголовок не найден.

- HTTP_QUERY_FLAG_REQUEST_HEADERS как правило, приложение запрашивает заголовки ответа, но приложения можно также запрашивать заголовки запроса с помощью этого флага.

- HTTP_QUERY_FLAG_SYSTEMTIME для заголовков, значение которого является строка даты и времени, например «Last-Modified-Time,» этот флаг возвращает значение заголовка как стандартный Win32 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуру, которая не требует приложению синтаксический анализ данных. Если вы используете этот флаг, может потребоваться использовать `SYSTEMTIME` переопределения функции.

- HTTP_QUERY_FLAG_NUMBER для заголовков, значение которого является число, например код состояния, этот флаг возвращает данные, в виде 32-разрядное число.

См. в разделе **"Примечания"** раздел для получения списка возможных значений.

*lpvBuffer*<br/>
Указатель на буфер, получающий сведения.

*lpdwBufferLength*<br/>
На запись это указывает на значение, содержащее длину буфера данных, в число символов или байтов. См. в разделе **"Примечания"** разделе более подробные сведения об этом параметре.

*lpdwIndex*<br/>
Указатель на индекс (с нуля) заголовка. Может иметь значение NULL. Этот флаг используется для перечисления нескольких заголовков с тем же именем. Во входных данных *lpdwIndex* указывает индекс указанного заголовка для возврата. На выводе *lpdwIndex* указывает индекс следующего заголовка. Если не удается найти следующий индекс, то возвращается ERROR_HTTP_HEADER_NOT_FOUND.

*str*<br/>
Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, получающий возвращенные сведения.

*dwIndex*<br/>
Значение индекса. См. в разделе *lpdwIndex*.

*pSysTime*<br/>
Указатель на Win32 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) структуры.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или на `CHttpFile` успешно созданного объектом [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Вы можете получить следующие типы данных из `QueryInfo`:

- строки (по умолчанию)

- `SYSTEMTIME` (для «данных:» «Expires:» д, заголовки)

- DWORD (для STATUS_CODE, CONTENT_LENGTH т. д.)

Когда строка записывается в буфер, а функция-член завершается успешно, `lpdwBufferLength` содержит длину строки в символах, за вычетом 1 для завершающего нуль-символа.

Возможные *dwInfoLevel* значениям относятся:

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

##  <a name="queryinfostatuscode"></a>  CHttpFile::QueryInfoStatusCode

Вызывайте эту функцию члена, чтобы получить код состояния, связанный с HTTP-запроса и поместите его в предоставленном *dwStatusCode* параметра.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Параметры

*dwStatusCode*<br/>
Ссылка на код состояния. Коды состояний обозначают успех или сбой запрошенного события. См. в разделе **"Примечания"** для выбора описания кода состояния.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или на `CHttpFile` успешно созданного объектом [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Коды состояния HTTP делятся на группы, об успехе или неудаче запроса. В следующих таблицах представлены группы кодов состояния и наиболее распространенные коды состояния HTTP.

|Группа|Значение|
|-----------|-------------|
|200-299|Success|
|300-399|Сведения|
|400-499|Ошибка запроса|
|500-599|Ошибка сервера|

Стандартные коды состояния HTTP:

|Код состояния|Значение|
|-----------------|-------------|
|200|Найти, URL-адрес следующим передачи|
|400|Прочитать запрос|
|404|Запрошенный URL-адрес не найден|
|405|Сервер не поддерживает запрошенный метод|
|500|Неизвестная ошибка сервера|
|503|Достигнута предельная вместимость сервера|

##  <a name="sendrequest"></a>  CHttpFile::SendRequest

Вызов этой функции-члена для отправки запроса на HTTP-сервер.

```
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLen = 0,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);

BOOL SendRequest(
    CString& strHeaders,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);
```

### <a name="parameters"></a>Параметры

*pstrHeaders*<br/>
Указатель на строку, содержащую имя заголовки для отправки.

*dwHeadersLen*<br/>
Длина заголовков, идентифицируемый *pstrHeaders*.

*lpOptional*<br/>
Необязательные данные для отправки сразу же после заголовки запроса. Обычно это используется для операции POST и PUT. Это может быть значение NULL, если отсутствуют дополнительные данные для отправки.

*dwOptionalLen*<br/>
Длина *lpOptional*.

*strHeaders*<br/>
Строка, содержащая имя заголовки для отправляемого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

##  <a name="sendrequestex"></a>  CHttpFile::SendRequestEx

Вызов этой функции-члена для отправки запроса на HTTP-сервер.

```
BOOL SendRequestEx(
    DWORD dwTotalLen,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);

BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,
    LPINTERNET_BUFFERS lpBuffOut,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*dwTotalLen*<br/>
Число байтов, отправляемых в запросе.

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов, см. в разделе [HttpSendRequestEx](/windows/desktop/api/wininet/nf-wininet-httpsendrequestexa) в пакете Windows SDK.

*dwContext*<br/>
Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. "Примечания".

*lpBuffIn*<br/>
Указатель на инициализированный [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) , описывающий входной буфер, используемый для операции.

*lpBuffOut*<br/>
Указатель на инициализированный INTERNET_BUFFERS, который описывает выходной буфер, используемый для операции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, при успешном выполнении. Если вызов завершается сбоем, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.

### <a name="remarks"></a>Примечания

Эта функция позволяет приложению отправлять данные с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) и [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`. Необходимо знать длину данных для отправки перед вызовом этой функции переопределять. Первое переопределение можно указать длину данных, которые вы хотите отправить. Второе переопределение принимает указатели на INTERNET_BUFFERS структуры, которые можно использовать для описания буфера в подробностях.

После записи содержимого в файл, вызовите [EndRequest](#endrequest) для завершения операции.

Значение по умолчанию для *dwContext* отправленные MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию присвоено значение по своему выбору, идентификатор контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния в объекте, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

### <a name="example"></a>Пример

Этот фрагмент кода отправляет содержимое строки в библиотеку DLL с именем MFCISAPI. Библиотека DLL на сервере LOCALHOST. Хотя в этом примере используется только один вызов `WriteString`, с помощью нескольких вызовов для отправки данных в блоках приемлемо.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>См. также

[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)
