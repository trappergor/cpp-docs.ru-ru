---
title: Класс CHttpFile | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e9af23bb74ba8e96f29a5b7cc4139d2932df8c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="chttpfile-class"></a>Класс CHttpFile
Предоставляет функции для запроса и чтения файлов на HTTP-сервере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>Участники  
  
### <a name="protected-constructors"></a>Защищенные конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|Создает объект `CHttpFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Добавляет заголовки запроса, отправленного в HTTP-сервер.|  
|[CHttpFile::EndRequest](#endrequest)|Завершает запрос, отправленный на HTTP-сервер с [SendRequestEx](#sendrequestex) функции-члена.|  
|[CHttpFile::GetFileURL](#getfileurl)|Получает URL-адрес для указанного файла.|  
|[CHttpFile::GetObject](#getobject)|Возвращает целевой объект команды в запросе на HTTP-сервер.|  
|[CHttpFile::GetVerb](#getverb)|Возвращает команду, которая использовалась в запросе на HTTP-сервер.|  
|[CHttpFile::QueryInfo](#queryinfo)|Возвращает заголовки запроса или ответа от сервера HTTP.|  
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Возвращает код состояния, связанный с HTTP-запроса и помещает его в предоставленном `dwStatusCode` параметра.|  
|[CHttpFile::SendRequest](#sendrequest)|Отправляет запрос HTTP-сервер.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Отправляет запрос к серверу HTTP с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) или [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`.|  
  
## <a name="remarks"></a>Примечания  
 Если Интернет-сеанс считывает данные из HTTP-сервер, необходимо создать экземпляр `CHttpFile`.  
  
 Дополнительные сведения о том, как `CHttpFile` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [Классе CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders  
 Вызовите эту функцию-член для добавления одного или обрабатывать дополнительные заголовки HTTP-запросов в HTTP-запрос.  
  
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
 Указатель на строку, содержащую заголовок или заголовки, чтобы добавить в запрос. Каждый заголовок должна заканчиваться точкой пару CR/LF.  
  
 `dwFlags`  
 Изменяет семантику новых заголовков. Ниже указаны доступные значения.  
  
- `HTTP_ADDREQ_FLAG_COALESCE`Объединяет заголовки с тем же именем, с помощью флага, чтобы добавить первый заголовок найден в последующих заголовок. Например «Accept: текст / *» следуют» Accept: аудио /\*» приводит формирование один заголовок» Accept: текст /\*аудио /\*». Именно вызывающего приложения для обеспечения целостного схему по отношению к данных, полученных запросов, отправленных с заголовками объединенное или разных.  
  
- `HTTP_ADDREQ_FLAG_REPLACE`Выполняет удаление и добавление для замены текущего заголовка. Имя заголовка будет использоваться для удаления текущего заголовка, а полное значение будет использоваться для добавления нового заголовка. Если значение заголовка является пустым и заголовок найден, он удаляется. Если это не пустой, значение заголовка заменяется.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`Добавляет заголовок только в том случае, если он еще не существует. Если оно существует, возвращается ошибка.  
  
- `HTTP_ADDREQ_FLAG_ADD`Использовать with REPLACE. Добавляет заголовок, если он не существует.  
  
 `dwHeadersLen`  
 Длина в символах для `pstrHeaders`. Если это значение-1 L, затем `pstrHeaders` считается нулем и вычисляется длина.  
  
 `str`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий заголовка запроса или добавлять заголовки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `AddRequestHeaders`Добавляет заголовки дополнительные, произвольном формате дескриптора запроса HTTP. Он предназначен для использования сложные клиенты, которым требуется подробный контроль над запросом на точное, отправляются на сервер HTTP.  
  
> [!NOTE]
>  Можно передать в нескольких заголовков в `pstrHeaders` или `str` для `AddRequestHeaders` вызовы с использованием `HTTP_ADDREQ_FLAG_ADD` или `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Если приложение пытается удалить или заменить заголовок с помощью **HTTP_ADDREQ_FLAG_REMOVE** или `HTTP_ADDREQ_FLAG_REPLACE`, могут быть заданы только один коннектор в `lpszHeaders`.  
  
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
 Указатель на строку, содержащую метод, используемый при отправке запроса. Может быть **POST**, **HEAD**, или `GET`.  
  
 dwContext  
 Идентификатор контекста для `CHttpFile` объекта. В разделе **примечания** Дополнительные сведения об этом параметре.  
  
 `pConnection`  
 Указатель на [CHttpConnection](../../mfc/reference/chttpconnection-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CHttpFile` объекта напрямую; вместо этого вызовите [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) вместо него.  
  
 Значение по умолчанию для `dwContext` отправленных MFC, позволяющий `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове `CInternetSession::OpenURL` или `CHttpConnection` для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние для объекта, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="endrequest"></a>CHttpFile::EndRequest  
 Вызовите эту функцию-член для завершения запроса, отправленного в HTTP-сервер с [SendRequestEx](#sendrequestex) функции-члена.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Флаги, описывающие операцию. Список соответствующих флагов см. в разделе [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) в Windows SDK.  
  
 `lpBuffIn`  
 Указатель на инициализированный [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , описывающий входной буфер, используемый для операции.  
  
 `dwContext`  
 Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. заметки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Значение по умолчанию для `dwContext` отправленных MFC, позволяющий `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние для объекта, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="getfileurl"></a>CHttpFile::GetFileURL  
 Вызовите эту функцию-член для получения имени файла HTTP URL-адрес.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий URL-адрес, ссылка на ресурс, связанный с этим файлом.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getobject"></a>CHttpFile::GetObject  
 Вызовите эту функцию-член для получения имени объекта, связанного с данным `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя объекта.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getverb"></a>CHttpFile::GetVerb  
 Вызовите эту функцию-член для получения HTTP команды (или метода) связанный с этим `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, содержащий имя HTTP-команды (или метод).  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
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
 Сочетание атрибутов для запросов и следующие флаги, указывающие тип запрошенные данные:  
  
- **HTTP_QUERY_CUSTOM** находит имя заголовка и возвращает это значение в `lpvBuffer` на выходе. **HTTP_QUERY_CUSTOM** выдает утверждение, если заголовок не найден.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** обычно приложение запрашивает заголовки ответа, но приложение также можно запрашивать с помощью этого флага заголовки запроса.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** для этих заголовков, значение которого является строки даты и времени, например «Last-Modified-Time,» этот флаг возвращает значение заголовка как стандартная Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуру, которая не требуется приложение для анализа данных. Если вы используете этот флаг, можно использовать `SYSTEMTIME` переопределение функции.  
  
- **HTTP_QUERY_FLAG_NUMBER** для этих заголовков, значение которого является число, например код состояния, этот флаг возвращает данные в виде 32-разрядное число.  
  
 В разделе **примечания** раздел список возможных значений.  
  
 `lpvBuffer`  
 Указатель на буфер, получающий данные.  
  
 `lpdwBufferLength`  
 При входе в это указывает на значение, содержащее длину буфера данных, в число символов или байтов. В разделе **примечания** статьи более подробные сведения об этом параметре.  
  
 `lpdwIndex`  
 Указатель на индекс (с нуля) заголовка. Может быть **NULL**. Этот флаг используется для перечисления несколько заголовков с тем же именем. На входе `lpdwIndex` определяет индекс указанного заголовка для возврата. На выходе `lpdwIndex` указывает индекс следующий заголовок. Если не удается найти следующий индекс, **ERROR_HTTP_HEADER_NOT_FOUND** возвращается.  
  
 `str`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объекта, который получает возвращенные сведения.  
  
 `dwIndex`  
 Значение индекса. См. раздел `lpdwIndex`.  
  
 *pSysTime*  
 Указатель на объект Win32 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Вы можете получить следующие типы данных из `QueryInfo`:  
  
-   строки (по умолчанию)  
  
- `SYSTEMTIME`(для «данных:» «Expires:» и т. д, заголовки)  
  
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
 Вызовите эту функцию-член, чтобы получить код состояния, связанные с HTTP-запроса и поместите его в предоставленном `dwStatusCode` параметра.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `dwStatusCode`  
 Ссылка на код состояния. Коды состояния указывают успешности запрошенное событие. В разделе **примечания** для выбора описания кодов состояния.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте эту функцию-член только после успешного вызова [SendRequest](#sendrequest) или `CHttpFile` объекта успешно создан, [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Коды состояния HTTP делятся на группы, об успехе или неудаче запроса. Следующие таблицы указаны группы кодов состояния и наиболее распространенные коды состояния HTTP.  
  
|Группа|Значение|  
|-----------|-------------|  
|200-299|Success|  
|300-399|Сведения|  
|400-499|Ошибка запроса|  
|500-599|Ошибка сервера|  
  
 Стандартные коды состояния HTTP:  
  
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
 Указатель на строку, содержащую имя заголовки для отправки.  
  
 `dwHeadersLen`  
 Длина заголовков, обозначенную `pstrHeaders`.  
  
 `lpOptional`  
 Дополнительные данные для отправки сразу после заголовков запроса. Обычно используется для **POST** и **ПОМЕСТИТЬ** операций. Это может быть **NULL** Если отсутствуют дополнительные данные для отправки.  
  
 *dwOptionalLen*  
 Длина `lpOptional`.  
  
 `strHeaders`  
 Строка, содержащая имя заголовки для отправляемого запроса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
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
 Флаги, описывающие операцию. Список соответствующих флагов см. в разделе [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) в Windows SDK.  
  
 `dwContext`  
 Идентификатор контекста для `CHttpFile` операции. Дополнительные сведения об этом параметре см. заметки.  
  
 `lpBuffIn`  
 Указатель на инициализированный [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , описывающий входной буфер, используемый для операции.  
  
 *lpBuffOut*  
 Указатель на инициализированный **INTERNET_BUFFERS** , описывающее выходной буфер, используемый для операции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, в случае успешного выполнения. При сбое вызова, определите причину сбоя, изучив порождается [CInternetException](../../mfc/reference/cinternetexception-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Эта функция позволяет приложению отправлять данные с помощью [записи](../../mfc/reference/cinternetfile-class.md#write) и [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) методы `CInternetFile`. Необходимо знать длину данных для отправки перед вызовом этой функции переопределять. Первый переопределения можно указать длину данных, которые необходимо отправить. Второй переопределение принимает указатели на **INTERNET_BUFFERS** структуры, которые можно использовать для описания буфера максимально подробно.  
  
 После содержимого записывается в файл, вызовите метод [EndRequest](#endrequest) для завершения операции.  
  
 Значение по умолчанию для `dwContext` отправленных MFC, позволяющий `CHttpFile` объекта из [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан `CHttpFile` объекта. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для создания `CHttpFile` объекта, можно переопределить значение по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние для объекта, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
### <a name="example"></a>Пример  
 Этот фрагмент кода библиотеки DLL с именем MFCISAPI отправляет содержимое строки. Библиотеки DLL на сервере LOCALHOST. Хотя в этом примере используется только один вызов `WriteString`, использование нескольких вызовов для отправки данных в блоках допустимо.  
  
 [!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс классе CInternetFile](../../mfc/reference/cinternetfile-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)
