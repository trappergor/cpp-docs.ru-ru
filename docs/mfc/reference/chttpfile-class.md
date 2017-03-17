---
title: "Класс CHttpFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- HTTP files
- HTTP requests, requesting and reading files
- CHttpFile class
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
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
ms.openlocfilehash: 0077c04f53514901dccaa3d162cd132578270225
ms.lasthandoff: 02/24/2017

---
# <a name="chttpfile-class"></a>Класс CHttpFile
Предоставляет функции для запроса и чтения файлов на HTTP-сервере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|Создает объект `CHttpFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Добавляет заголовки запроса, отправленного на HTTP-сервер.|  
|[CHttpFile::EndRequest](#endrequest)|Завершает запрос, отправленный на HTTP-сервер с [SendRequestEx](#sendrequestex) функции-члена.|  
|[CHttpFile::GetFileURL](#getfileurl)|Возвращает URL-адрес для указанного файла.|  
|[CHttpFile::GetObject](#getobject)|Возвращает целевой объект команды в запросе к HTTP-серверу.|  
|[CHttpFile::GetVerb](#getverb)|Возвращает команду, которая использовалась в запросе к HTTP-серверу.|  
|[CHttpFile::QueryInfo](#queryinfo)|Возвращает заголовки запроса или ответа от сервера HTTP.|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Возвращает код состояния, связанный с HTTP-запрос и помещает его в предоставленном `dwStatusCode` параметр.|  
|[CHttpFile::SendRequest](#sendrequest)|Отправляет запрос на HTTP-сервер.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Отправляет запрос серверу HTTP с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) или [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`.|  
  
## <a name="remarks"></a>Примечания  
 Если Интернет-сеанс считывает данные из HTTP-сервере, необходимо создать экземпляр `CHttpFile`.  
  
 Дополнительные сведения о том, как `CHttpFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders  
 Вызов этой функции-члена для добавления одного или обрабатывать дополнительные заголовки HTTP-запросов в HTTP-запрос.  
  
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
 `pstrHeaders`  
 Указатель на строку, содержащую заголовок или заголовки, чтобы добавить в запрос. Каждый заголовок, должна заканчиваться парой возврат каретки.  
  
 `dwFlags`  
 Изменяет семантику новых заголовков. Ниже указаны доступные значения.  
  
- `HTTP_ADDREQ_FLAG_COALESCE`Объединяет заголовки с тем же именем, с использованием флага, чтобы добавить первый заголовок найден в последующих заголовок. Например» принять: текст или *» следуют» принять: аудио и\*» приводит формирование один заголовок» принять: текст или\*, аудио и\*». Это зависит от вызывающего приложения для обеспечения связный схемы по отношению к данных, полученных запросов, отправленных с заголовками совместно или отдельно.  
  
- `HTTP_ADDREQ_FLAG_REPLACE`Выполняет удаление и добавление для замены текущего заголовка. Имя заголовка будет использоваться для удаления текущего заголовка, а полное значение будет использоваться для добавления нового заголовка. Если значение заголовка является пустым и заголовок найден, он удаляется. Если не пустое, заменяется значением заголовка.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`Добавляет заголовок только в том случае, если он еще не существует. Если он существует, возвращается ошибка.  
  
- `HTTP_ADDREQ_FLAG_ADD`Используется с функцией REPLACE. Добавляет заголовок, если она не существует.  
  
 `dwHeadersLen`  
 Длина в символах для `pstrHeaders`. Если это значение-1 L, затем `pstrHeaders` считается нулем и вычисляется длина.  
  
 `str`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий заголовка запроса или добавлять заголовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `AddRequestHeaders`Добавляет дополнительные, свободный формат заголовков для обработки запроса HTTP. Он предназначен для использования клиентами сложные, требующие тщательного контроля за точный запрос, отправляемый HTTP-сервера.  
  
> [!NOTE]
>  Можно передать в нескольких заголовков в `pstrHeaders` или `str` для `AddRequestHeaders` вызов с использованием `HTTP_ADDREQ_FLAG_ADD` или `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Если приложение пытается удалить или заменить заголовок с помощью **HTTP_ADDREQ_FLAG_REMOVE** или `HTTP_ADDREQ_FLAG_REPLACE`, могут быть заданы только один заголовок в `lpszHeaders`.  
  
##  <a name="chttpfile"></a>CHttpFile::CHttpFile  
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
 `hFile`  
 Дескриптор файла Интернета.  
  
 `hSession`  
 Дескриптор для Интернет-сеанс.  
  
 *pstrObject*  
 Указатель на строку, содержащую `CHttpFile` объекта.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера.  
  
 `pstrVerb`  
 Указатель на строку, содержащую метод, используемый при отправке запроса. Can be **POST**, **HEAD**, or `GET`.  
  
 dwContext  
 Идентификатор контекста для `CHttpFile` объекта. В разделе **примечания** Дополнительные сведения об этом параметре.  
  
 `pConnection`  
 Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CHttpFile` напрямую; вместо этого вызвать [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) вместо.  
  
 Значение по умолчанию для `dwContext` отправленных MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) создания объекта `CHttpFile` объекта. При вызове `CInternetSession::OpenURL` или `CHttpConnection` для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния объекта, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="endrequest"></a>CHttpFile::EndRequest  
 Вызов этой функции-члена для завершения запроса, отправленного на HTTP-сервер с [SendRequestEx](#sendrequestex) функции-члена.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Флаги, описывающие операцию. Список соответствующие флаги, в разделе [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpBuffIn`  
 Указатель на инициализированный [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , описывающий входной буфер, используемый для операции.  
  
 `dwContext`  
 Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. заметки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для `dwContext` отправленных MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) создания объекта `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния объекта, с помощью которого определяется. В статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="getfileurl"></a>CHttpFile::GetFileURL  
 Вызовите эту функцию-член для получения имени файла HTTP URL-адреса.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес ссылки на ресурс, связанный с этим файлом.  
  
### <a name="remarks"></a>Примечания  
 Использовать только после успешного вызова функции-члена [SendRequest](#sendrequest) или `CHttpFile` объект успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getobject"></a>CHttpFile::GetObject  
 Вызовите эту функцию-член для получения имени объекта, связанного с этим `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя объекта.  
  
### <a name="remarks"></a>Примечания  
 Использовать только после успешного вызова функции-члена [SendRequest](#sendrequest) или `CHttpFile` объект успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getverb"></a>CHttpFile::GetVerb  
 Вызовите эту функцию-член для получения HTTP команды (или метода) связанный с этим `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя HTTP-команда (или метод).  
  
### <a name="remarks"></a>Примечания  
 Использовать только после успешного вызова функции-члена [SendRequest](#sendrequest) или `CHttpFile` объект успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="queryinfo"></a>CHttpFile::QueryInfo  
 Вызовите эту функцию-член для возврата ответа или заголовки запроса из HTTP-запроса.  
  
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
 `dwInfoLevel`  
 Сочетание атрибутов для запроса и следующие флаги, указывающие тип запрашиваемые сведения:  
  
- **HTTP_QUERY_CUSTOM** находит имя заголовка и возвращает это значение в `lpvBuffer` на выходе. **HTTP_QUERY_CUSTOM** создает утверждение, если заголовок не найден.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** обычно приложение запрашивает заголовки ответа, но приложения могут также запрашивать заголовков запроса с помощью этого флага.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** для этих заголовков, значение которого является строка даты и времени, например «Last-Modified-Time,» этот флаг возвращает значение заголовка как стандартная Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая не требует приложение для анализа данных. Если используется этот флаг, можно использовать `SYSTEMTIME` переопределения функции.  
  
- **HTTP_QUERY_FLAG_NUMBER** для этих заголовков, значение которого является число, например код состояния, этот флаг возвращает данные в виде 32-разрядное число.  
  
 В разделе **примечания** раздел для получения списка возможных значений.  
  
 `lpvBuffer`  
 Указатель на буфер, получающий данные.  
  
 `lpdwBufferLength`  
 Операции это указывает на значение, содержащее длину буфера данных, в число символов или байтов. В разделе **примечания** статьи более подробные сведения об этом параметре.  
  
 `lpdwIndex`  
 Указатель на индекс (с нуля) заголовка. Может быть **NULL**. Этот флаг используется для перечисления нескольких заголовков с тем же именем. На входе `lpdwIndex` указывает индекс указанного заголовка для возврата. На выходе `lpdwIndex` указывает индекс следующего заголовка. Если не удается найти следующий индекс, **ERROR_HTTP_HEADER_NOT_FOUND** возвращается.  
  
 `str`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, который получает возвращенные сведения.  
  
 `dwIndex`  
 Значение индекса. См. раздел `lpdwIndex`.  
  
 *pSysTime*  
 Указатель на объект Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Использовать только после успешного вызова функции-члена [SendRequest](#sendrequest) или `CHttpFile` объект успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Можно получить следующие типы данных из `QueryInfo`:  
  
-   строки (по умолчанию)  
  
- `SYSTEMTIME`(для «данных: ««Expires:» и т. д, заголовки)  
  
- `DWORD`(для **STATUS_CODE**, **CONTENT_LENGTH**и т. д.)  
  
 Если строка записывается в буфер, а функция-член завершается успешно, `lpdwBufferLength` содержит длину строки в символах минус 1 для завершения **NULL** символов.  
  
 Возможные `dwInfoLevel` значения включают:  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>CHttpFile::QueryInfoStatusCode  
 Вызовите эту функцию-член для получения код состояния, связанный с HTTP-запроса и поместите его в предоставленном `dwStatusCode` параметр.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwStatusCode`  
 Ссылка на код состояния. Коды состояния указать успех или сбой запрошенного события. В разделе **примечания** для выбора описания кодов состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Использовать только после успешного вызова функции-члена [SendRequest](#sendrequest) или `CHttpFile` объект успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Коды состояния HTTP делятся на группы, об успехе или неудаче запроса. Следующие таблицы показывают, как группы кода состояния и наиболее распространенные коды состояния HTTP.  
  
|Группа|Значение|  
|-----------|-------------|  
|200-299|Success|  
|300-399|Сведения|  
|400-499|Ошибка запроса|  
|500-599|Ошибка сервера|  
  
 Основные коды состояния HTTP:  
  
|Код состояния|Значение|  
|-----------------|-------------|  
|200|URL-адрес находится ниже передачи|  
|400|Нельзя расшифровать запрос|  
|404|Запрошенный URL-адрес не найден|  
|405|Сервер не поддерживает запрошенный метод|  
|500|Неизвестная ошибка сервера|  
|503|Достигнут емкости сервера|  
  
##  <a name="sendrequest"></a>CHttpFile::SendRequest  
 Вызовите эту функцию-член для отправки запроса на HTTP-сервер.  
  
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
 `pstrHeaders`  
 Указатель на строку, содержащую имя заголовков для отправки.  
  
 `dwHeadersLen`  
 Длина заголовков, идентифицируемый `pstrHeaders`.  
  
 `lpOptional`  
 Необязательные данные для отправки сразу после заголовков запроса. Обычно используется для **POST** и **ПОМЕСТИТЬ** операций. Это может быть **NULL** Если отсутствуют необязательные данные для отправки.  
  
 *dwOptionalLen*  
 Длина `lpOptional`.  
  
 `strHeaders`  
 Строка, содержащая имя заголовки для отправляемого запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
##  <a name="sendrequestex"></a>CHttpFile::SendRequestEx  
 Вызовите эту функцию-член для отправки запроса на HTTP-сервер.  
  
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
 *dwTotalLen*  
 Число байтов, отправляемых в запросе.  
  
 `dwFlags`  
 Флаги, описывающие операцию. Список соответствующие флаги, в разделе [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 `dwContext`  
 Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. заметки.  
  
 `lpBuffIn`  
 Указатель на инициализированный [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , описывающий входной буфер, используемый для операции.  
  
 *lpBuffOut*  
 Указатель на инициализированный **INTERNET_BUFFERS** , описывающий выходной буфер, используемый для операции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения. Если вызов завершается сбоем, определите причину сбоя, изучив вызванное [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет приложению отправлять данные с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) и [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`. Необходимо знать длину данных для отправки перед вызовом этой функции переопределять. Первый переопределение можно указать длину данных, которые вы хотите отправить. Второй переопределенный метод принимает указатели на **INTERNET_BUFFERS** структуры, которые могут использоваться для описания буфера в подробностях.  
  
 После содержимого записывается в файл, вызовите метод [EndRequest](#endrequest) для завершения операции.  
  
 Значение по умолчанию для `dwContext` отправленных MFC для `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) создания объекта `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния объекта, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода отправляет содержимое строки в DLL с именем MFCISAPI. Библиотеки DLL на сервере LOCALHOST. Хотя в этом примере используется только один вызов `WriteString`, с помощью нескольких вызовов для отправки данных в блоках приемлемо.  
  
 [!code-cpp[NVC_MFCWinInet №&9;](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)

