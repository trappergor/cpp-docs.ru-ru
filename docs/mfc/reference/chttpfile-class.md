---
title: Класс Чттпфиле
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
ms.openlocfilehash: ff050a89a10c68c639c141891dd51b1b2d58e105
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915998"
---
# <a name="chttpfile-class"></a>Класс Чттпфиле

Предоставляет функции для запроса и чтения файлов на HTTP-сервере.

## <a name="syntax"></a>Синтаксис

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|name|Описание|
|----------|-----------------|
|[Чттпфиле:: Чттпфиле](#chttpfile)|Создает объект `CHttpFile`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Чттпфиле:: Аддрекуессеадерс](#addrequestheaders)|Добавляет заголовки в запрос, отправленный на HTTP-сервер.|
|[Чттпфиле:: EndRequest](#endrequest)|Завершает запрос, отправленный на HTTP-сервер с помощью функции-члена [сендрекуестекс](#sendrequestex) .|
|[Чттпфиле:: Жетфилеурл](#getfileurl)|Возвращает URL-адрес для указанного файла.|
|[Чттпфиле:: GetObject](#getobject)|Возвращает целевой объект команды в запросе к HTTP-серверу.|
|[CHttpFile::GetVerb](#getverb)|Возвращает команду, которая использовалась в запросе к HTTP-серверу.|
|[Чттпфиле:: Куеринфо](#queryinfo)|Возвращает ответ или заголовки запросов с HTTP-сервера.|
|[Чттпфиле:: Куеринфостатускоде](#queryinfostatuscode)|Извлекает код состояния, связанный с HTTP-запросом, и помещает его `dwStatusCode` в указанный параметр.|
|[CHttpFile::SendRequest](#sendrequest)|Отправляет запрос на HTTP-сервер.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Отправляет запрос на HTTP-сервер с помощью `CInternetFile`методов [Write](../../mfc/reference/cinternetfile-class.md#write) или [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) .|

## <a name="remarks"></a>Примечания

Если сеанс Интернета считывает данные с HTTP-сервера, необходимо создать экземпляр `CHttpFile`.

Дополнительные сведения о `CHttpFile` работе с другими классами Интернета MFC см. в статье Интернет – [программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[кфиле](../../mfc/reference/cfile-class.md)

[кстдиофиле](../../mfc/reference/cstdiofile-class.md)

[Цинтернетфиле](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет. h

##  <a name="addrequestheaders"></a>Чттпфиле:: Аддрекуессеадерс

Вызовите эту функцию-член, чтобы добавить один или несколько заголовков HTTP-запроса в обработчик HTTP-запроса.

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

*пстрхеадерс*<br/>
Указатель на строку, содержащую заголовок или заголовки для добавления к запросу. Каждый заголовок должен быть завершен парой CR/LF.

*dwFlags*<br/>
Изменяет семантику новых заголовков. Ниже указаны доступные значения.

- HTTP_ADDREQ_FLAG_COALESCE объединяет заголовки с одним и тем же именем с помощью флага, чтобы добавить первый заголовок, найденный в последующем заголовке. Например, "\*Accept: Text/", а затем "Accept: Audio/\*" приводит к формированию одного заголовка "Accept: Text/\*, Audio/\*". Для обеспечения согласованной схемы с данными, полученными запросами, отправленными с объединенными или отдельными заголовками, используется вызывающее приложение.

- HTTP_ADDREQ_FLAG_REPLACE выполняет операцию удаления и добавления для замены текущего заголовка. Имя заголовка будет использоваться для удаления текущего заголовка, а для добавления нового заголовка будет использовано полное значение. Если заголовок-значение пусто и заголовок найден, он удаляется. Если значение не пусто, заменяется заголовок-value.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW добавляет заголовок, только если он еще не существует. Если он существует, возвращается ошибка.

- HTTP_ADDREQ_FLAG_ADD используется с параметром Replace. Добавляет заголовок, если он не существует.

*двхеадерслен*<br/>
Длина *пстрхеадерс*в символах. Если задано значение-1L, то предполагается, что *пстрхеадерс* завершается нулем и длина вычислена.

*str*<br/>
Ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий добавляемый заголовок запроса или заголовки.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

`AddRequestHeaders`Добавляет дополнительные заголовки свободного формата к обработчику HTTP-запроса. Он предназначен для использования сложными клиентами, которым необходим подробный контроль над точным запросом, отправляемым на HTTP-сервер.

> [!NOTE]
>  Приложение может передавать несколько заголовков в *пстрхеадерс* или *str* для `AddRequestHeaders` вызова с помощью HTTP_ADDREQ_FLAG_ADD или HTTP_ADDREQ_FLAG_ADD_IF_NEW. Если приложение пытается удалить или заменить заголовок с помощью HTTP_ADDREQ_FLAG_REMOVE или HTTP_ADDREQ_FLAG_REPLACE, в *лпсзеадерс*можно указать только один заголовок.

##  <a name="chttpfile"></a>Чттпфиле:: Чттпфиле

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
Маркер для файла Интернета.

*хсессион*<br/>
Маркер сеанса Интернета.

*пстробжект*<br/>
Указатель на строку, содержащую `CHttpFile` объект.

*пстрсервер*<br/>
Указатель на строку, содержащую имя сервера.

*пстрверб*<br/>
Указатель на строку, содержащую метод, который должен использоваться при отправке запроса. Может быть POST, HEAD или GET.

*двконтекст*<br/>
Идентификатор контекста для `CHttpFile` объекта. Дополнительные сведения об этом параметре см. в разделе **"Примечания"** .

*пконнектион*<br/>
Указатель на объект [чттпконнектион](../../mfc/reference/chttpconnection-class.md) .

### <a name="remarks"></a>Примечания

Вы никогда не конструируете `CHttpFile` объект напрямую; вместо этого вызывайте [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [чттпконнектион:: опенрекуест](../../mfc/reference/chttpconnection-class.md#openrequest) .

Значение по умолчанию `dwContext` для отправляется MFC `CHttpFile` объекту из объекта [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) , который создал `CHttpFile` объект. При вызове `CInternetSession::OpenURL` метода `CHttpConnection` или для создания `CHttpFile` объекта можно переопределить значение по умолчанию, чтобы задать идентификатор контекста в качестве значения по своему усмотрению. Идентификатор контекста возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние для объекта, с которым он определен. См. статью [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) для получения дополнительных сведений об идентификаторе контекста.

##  <a name="endrequest"></a>Чттпфиле:: EndRequest

Вызовите эту функцию-член, чтобы завершить запрос, отправленный на HTTP-сервер с помощью функции-члена [сендрекуестекс](#sendrequestex) .

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов см. в разделе [хттпендрекуест](/windows/desktop/api/wininet/nf-wininet-httpendrequesta) в Windows SDK.

*лпбуффин*<br/>
Указатель на инициализированное [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-internet_buffersa) , описывающее входной буфер, используемый для операции.

*двконтекст*<br/>
Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, определите причину сбоя, изучив сгенерированный объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) .

### <a name="remarks"></a>Примечания

Значение по умолчанию для *dwContext* отправляется MFC объекту `CHttpFile` из объекта [CInternetSession](../../mfc/reference/cinternetsession-class.md), который создал объект `CHttpFile`. При вызове [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [чттпконнектион](../../mfc/reference/chttpconnection-class.md) `CHttpFile` для создания объекта можно переопределить значение по умолчанию, чтобы задать идентификатор контекста в качестве значения по своему усмотрению. Идентификатор контекста возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние для объекта, с которым он определен. См. [статью первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) для получения дополнительных сведений об идентификаторе контекста.

##  <a name="getfileurl"></a>Чттпфиле:: Жетфилеурл

Вызовите эту функцию-член, чтобы получить имя файла HTTP в виде URL-адреса.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий URL-адрес, ссылающийся на ресурс, связанный с этим файлом.

### <a name="remarks"></a>Примечания

Эту функцию-член следует использовать только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта, успешно созданного [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getobject"></a>Чттпфиле:: GetObject

Вызовите эту функцию члена, чтобы получить имя объекта, связанного с этим `CHttpFile`объектом.

```
CString GetObject() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий имя объекта.

### <a name="remarks"></a>Примечания

Эту функцию-член следует использовать только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта, успешно созданного [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getverb"></a>Чттпфиле:: verb

Вызовите эту функцию-член, чтобы получить команду HTTP (или метод), `CHttpFile`связанную с этим объектом.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий имя HTTP-команды (или метода).

### <a name="remarks"></a>Примечания

Эту функцию-член следует использовать только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта, успешно созданного [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="queryinfo"></a>Чттпфиле:: Куеринфо

Вызовите эту функцию-член для возврата заголовков ответа или запроса из HTTP-запроса.

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

*двинфолевел*<br/>
Сочетание атрибута для запроса и следующие флаги, указывающие тип запрашиваемой информации:

- HTTP_QUERY_CUSTOM находит имя заголовка и возвращает это значение в *лпвбуффер* на выходе. HTTP_QUERY_CUSTOM создает утверждение, если заголовок не найден.

- HTTP_QUERY_FLAG_REQUEST_HEADERS Обычно приложение запрашивает заголовки ответа, но приложение может также запрашивать заголовки запросов с помощью этого флага.

- HTTP_QUERY_FLAG_SYSTEMTIME для этих заголовков, значение которых является строкой даты и времени, например "Last-Modified-Time", этот флаг возвращает значение заголовка как стандартную структуру Win32 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) , не требующую от приложения анализа данных. При использовании этого флага может потребоваться `SYSTEMTIME` переопределение функции.

- HTTP_QUERY_FLAG_NUMBER для этих заголовков, значение которых равно числу, например код состояния, этот флаг возвращает данные в виде 32-разрядного числа.

Список возможных значений см. в разделе **"Примечания** ".

*лпвбуффер*<br/>
Указатель на буфер, который получает данные.

*лпдвбуфферленгс*<br/>
В записи это указывает на значение, содержащее длину буфера данных в количестве символов или байтах. Более подробные сведения об этом параметре см. в разделе **"Примечания"** .

*лпдвиндекс*<br/>
Указатель на индекс заголовка, начинающийся с нуля. Может иметь значение NULL. Используйте этот флаг для перечисления нескольких заголовков с одним и тем же именем. На входе *лпдвиндекс* указывает индекс возвращаемого заголовка. В выходных данных *лпдвиндекс* указывает индекс следующего заголовка. Если не удается найти следующий индекс, возвращается ERROR_HTTP_HEADER_NOT_FOUND.

*str*<br/>
Ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , получающий возвращенные сведения.

*двиндекс*<br/>
Значение индекса. См. *лпдвиндекс*.

*псистиме*<br/>
Указатель на структуру Win32 [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) .

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

Эту функцию-член следует использовать только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта, успешно созданного [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Из `QueryInfo`можно получить следующие типы данных:

- строки (по умолчанию)

- `SYSTEMTIME`(для "Data:" срок действия истекает: "и т. д.)

- DWORD (для STATUS_CODE, CONTENT_LENGTH и т. д.)

Когда строка записывается в буфер и функция-член завершается, `lpdwBufferLength` содержит длину строки в символах минус 1 для завершающего нуль-символа.

Возможные значения *двинфолевел* включают:

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

##  <a name="queryinfostatuscode"></a>Чттпфиле:: Куеринфостатускоде

Вызовите эту функцию-член, чтобы получить код состояния, связанный с HTTP-запросом, и поместите его в указанный параметр *двстатускоде* .

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Параметры

*двстатускоде*<br/>
Ссылка на код состояния. Коды состояния указывают на успешность или сбой запрошенного события. См. раздел **Примечания** для выбора описания кода состояния.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

### <a name="remarks"></a>Примечания

Эту функцию-член следует использовать только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта, успешно созданного [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Коды состояния HTTP делятся на группы, указывающие на успешное выполнение или сбой запроса. В следующих таблицах представлены группы кодов состояния и наиболее распространенные коды состояния HTTP.

|Группа|Значение|
|-----------|-------------|
|200-299|Success|
|300-399|Сведения|
|400-499|Ошибка запроса|
|500-599|Ошибка сервера|

Распространенные коды состояния HTTP:

|status code|Значение|
|-----------------|-------------|
|200|URL-адрес расположен, передача проходит|
|400|Нечитаемый запрос|
|404|Запрошенный URL-адрес не найден|
|405|Сервер не поддерживает запрошенный метод|
|500|Неизвестная ошибка сервера|
|503|Достигнута емкость сервера|

##  <a name="sendrequest"></a>Чттпфиле:: SendRequest

Вызовите эту функцию-член, чтобы отправить запрос к серверу HTTP.

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

*пстрхеадерс*<br/>
Указатель на строку, содержащую имя заголовков для отправки.

*двхеадерслен*<br/>
Длина заголовков, идентифицируемых *пстрхеадерс*.

*лпоптионал*<br/>
Любые необязательные данные, отправляемые сразу после заголовков запроса. Обычно это используется для операций POST и постановки. Может иметь значение NULL, если нет дополнительных данных для отправки.

*двоптионаллен*<br/>
Длина *лпоптионал*.

*стрхеадерс*<br/>
Строка, содержащая имена заголовков отправляемого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, определите причину сбоя, изучив сгенерированный объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) .

##  <a name="sendrequestex"></a>Чттпфиле:: Сендрекуестекс

Вызовите эту функцию-член, чтобы отправить запрос к серверу HTTP.

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

*двтоталлен*<br/>
Число байтов, отправляемых в запросе.

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов см. в разделе [хттпсендрекуестекс](/windows/desktop/api/wininet/nf-wininet-httpsendrequestexa) в Windows SDK.

*двконтекст*<br/>
Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. в разделе "Примечания".

*лпбуффин*<br/>
Указатель на инициализированное [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-internet_buffersa) , описывающее входной буфер, используемый для операции.

*лпбуффаут*<br/>
Указатель на инициализированное INTERNET_BUFFERS, описывающее выходной буфер, используемый для операции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успеха. Если вызов завершается неудачно, определите причину сбоя, изучив сгенерированный объект [Цинтернетексцептион](../../mfc/reference/cinternetexception-class.md) .

### <a name="remarks"></a>Примечания

Эта функция позволяет приложению передавать данные с помощью методов `CInternetFile` [Write](../../mfc/reference/cinternetfile-class.md#write) и [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) . Необходимо иметь представление о длине данных для отправки перед вызовом любого переопределения этой функции. Первое переопределение позволяет указать длину данных, которые вы хотите отправить. Второе переопределение принимает указатели на структуры INTERNET_BUFFERS, которые можно использовать для подробного описания буфера.

После того как содержимое записывается в файл, вызовите метод [EndRequest](#endrequest) , чтобы завершить операцию.

Значение по умолчанию для *dwContext* отправляется MFC объекту `CHttpFile` из объекта [CInternetSession](../../mfc/reference/cinternetsession-class.md), который создал объект `CHttpFile`. При вызове [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [чттпконнектион](../../mfc/reference/chttpconnection-class.md) `CHttpFile` для создания объекта можно переопределить значение по умолчанию, чтобы задать идентификатор контекста в качестве значения по своему усмотрению. Идентификатор контекста возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние для объекта, с которым он определен. См. статью [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) для получения дополнительных сведений об идентификаторе контекста.

### <a name="example"></a>Пример

Этот фрагмент кода отправляет содержимое строки в библиотеку DLL с именем МФЦИСАПИ. DLL на сервере LOCALHOST. Хотя в этом примере используется только один вызов `WriteString`, Допускается использование нескольких вызовов для отправки данных в блоках.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>См. также

[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)
