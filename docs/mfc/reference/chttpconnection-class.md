---
title: "Класс CHttpConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- protocols, HTTP
- connecting to servers, HTTP servers
- Internet protocols, HTTP
- HTTP connections
- Internet protocols
- CHttpConnection class
- HTTP servers, connecting to
- connecting to servers
- Internet connections, HTTP
- connections [C++], HTTP
- Internet server, HTTP
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1b02a79cebbd73a05478887115646f0544f0a92d
ms.lasthandoff: 02/24/2017

---
# <a name="chttpconnection-class"></a>Класс CHttpConnection
Управление подключением к HTTP-серверу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|Создает объект `CHttpConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHttpConnection::OpenRequest](#openrequest)|Открытие HTTP-запроса.|  
  
## <a name="remarks"></a>Примечания  
 HTTP является одним из трех серверные протоколы Интернета, реализованы с помощью классов MFC WinInet.  
  
 Класс `CHttpConnection` содержит конструктор и один член функции, [OpenRequest](#openrequest), который управляет подключения к серверу с помощью протокола HTTP.  
  
 Для взаимодействия с HTTP-сервере, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создать [CHttpConnection](#_mfc_chttpconnection) объекта. Никогда не создавать `CHttpConnection` напрямую; вместо этого вызвать метод [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), который создает `CHttpConnection` объекта и возвращает указатель на него.  
  
 Дополнительные сведения о том, как `CHttpConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о подключении к серверам с использованием двух других поддерживаемых протоколов Интернета, gopher и FTP, в разделе классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="a-namechttpconnectiona--chttpconnectionchttpconnection"></a><a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 Эта функция-член вызывается для создания `CHttpConnection` объекта.  
  
```  
CHttpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pSession`  
 Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.  
  
 `hConnected`  
 Дескриптор для подключения к Интернету.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера.  
  
 `dwContext`  
 Идентификатор контекста для `CInternetConnection` объекта. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
 `nPort`  
 Число, идентифицирующее порт Интернета для данного подключения.  
  
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
  
 `dwFlags`  
 Любое сочетание **INTERNET_ FLAG_\* ** флаги. См. в таблице **примечания** раздел [CHttpConnection::OpenRequest](#openrequest) описание `dwFlags` значения.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CHttpConnection` напрямую. Вместо этого объекта создается путем вызова [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).  
  
##  <a name="a-nameopenrequesta--chttpconnectionopenrequest"></a><a name="openrequest"></a>CHttpConnection::OpenRequest  
 Вызовите эту функцию-член для открытия HTTP-соединения.  
  
```  
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

 
CHttpFile* OpenRequest(
    int nVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrVerb`  
 Указатель на строку, содержащую команду, которую необходимо использовать в запросе. Если `NULL`, используется «Получить».  
  
 `pstrObjectName`  
 Указатель на строку, содержащую целевой объект указанную команду. Обычно это имя файла, исполняемый модуль или описатель поиска.  
  
 `pstrReferer`  
 Указатель на строку, указывающую адрес (URL) документа, из которого URL-адрес в запросе ( `pstrObjectName`) был получен. Если `NULL`, указан без заголовка HTTP.  
  
 `dwContext`  
 Идентификатор контекста для `OpenRequest` операции. В разделе «Примечания» для получения дополнительной информации `dwContext`.  
  
 `ppstrAcceptTypes`  
 Указатель на массив нули из `LPCTSTR` указатели для строк, указывающих типы содержимого, принятый клиентом. Если `ppstrAcceptTypes` — `NULL`, серверы интерпретировать клиент принимает только документы типа «текст / *» (то есть только текстовых документов и не изображения или другие двоичные файлы). Тип содержимого является эквивалентом переменных CONTENT_TYPE CGI, который определяет тип данных для запросов, которые были присоединены сведения, такие как HTTP POST и PUT.  
  
 `pstrVersion`  
 Указатель на строку, определяющую версию HTTP. Если `NULL`, используется «HTTP/1.0».  
  
 `dwFlags`  
 Любое сочетание флагов INTERNET_ FLAG_ *. В разделе «Примечания» для описания возможных `dwFlags` значения.  
  
 `nVerb`  
 Номер, связанный с типом запроса HTTP. Ниже указаны доступные значения.  
  
|Тип запроса HTTP|Значение `nVerb`|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CHttpFile](../../mfc/reference/chttpfile-class.md) запрошенный объект.  
  
### <a name="remarks"></a>Примечания  
 `dwFlags` может принимать следующие значения:  
  
|Флаг Интернета|Описание|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|Вызывает принудительную загрузку запрошенного файла, объекта или просмотр каталога на исходном сервере, а не из кэша.|  
|`INTERNET_FLAG_DONT_CACHE`|Не добавляет возвращаемой сущности в кэш.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|Добавляет в кэш возвращаемой сущности как постоянные сущность. Это означает, что очистка кэша standard, проверки согласованности или сборщик мусора не удается удалить этот элемент из кэша.|  
|`INTERNET_FLAG_SECURE`|Безопасные транзакции используют семантику. Это означает использование SSL или PCT и применяется только в HTTP-запросов|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|Используется только с HTTP, указывает, что перенаправление не должен обрабатываться автоматически в [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Переопределение `dwContext` по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста связан с этой конкретной операции `CHttpConnection` объект, созданный его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния операции, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
 С помощью этой функции могут быть исключения.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)

