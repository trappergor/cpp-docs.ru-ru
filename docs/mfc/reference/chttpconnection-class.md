---
title: "Класс CHttpConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs: C++
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea35172c527d1dad62f2f565bf7cf2e25001323b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CHttpConnection::OpenRequest](#openrequest)|Открывает HTTP-запроса.|  
  
## <a name="remarks"></a>Примечания  
 HTTP является одним из трех server протоколы Интернета, реализованными этими классами MFC WinInet.  
  
 Класс `CHttpConnection` содержит конструктор и функция один член [OpenRequest](#openrequest), управляющий подключения к серверу с помощью протокола HTTP.  
  
 Для взаимодействия с HTTP-сервера, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создать [CHttpConnection](#_mfc_chttpconnection) объекта. Никогда не создавайте `CHttpConnection` объекта напрямую; вместо этого вызовите [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), которая создает `CHttpConnection` объекта и возвращает указатель на него.  
  
 Дополнительные сведения о том, как `CHttpConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о подключении к серверам с помощью две другие поддерживаемые протоколы Интернета, gopher и FTP, просмотреть классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) и [классе CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
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
 Число, определяющее порт Интернета для этого подключения.  
  
 `pstrUserName`  
 Указатель на строку с завершающим нулем, указывающее имя пользователя для входа. Если **NULL**, значение по умолчанию является анонимным.  
  
 `pstrPassword`  
 Указатель символом null строку, которая указывает пароль, используемый для входа. Если оба `pstrPassword` и `pstrUserName` , **NULL**, анонимных паролей по умолчанию является имя электронной почты пользователя. Если `pstrPassword` — **NULL** (или пустую строку), но `pstrUserName` не **NULL**, используется пустой пароль. В следующей таблице описаны поведение для четыре возможные параметры `pstrUserName` и `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|Имя пользователя, отправленных FTP-сервер|Пароль, отправленных FTP-сервер|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**Значение NULL** или «»|**Значение NULL** или «»|«anonymous»|Имя электронной почты пользователя|  
|Не- **NULL** строки|**Значение NULL** или «»|`pstrUserName`|" "|  
|**Значение NULL** отличных **NULL** строки|**ОШИБКА**|**ОШИБКА**||  
|Не- **NULL** строки|Не- **NULL** строки|`pstrUserName`|`pstrPassword`|  
  
 `dwFlags`  
 Любое сочетание **INTERNET_ FLAG_\***  флаги. См. в таблице **примечания** раздел [CHttpConnection::OpenRequest](#openrequest) описание `dwFlags` значения.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CHttpConnection` напрямую. Вместо этого объекта создается путем вызова [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).  
  
##  <a name="openrequest"></a>CHttpConnection::OpenRequest  
 Вызовите эту функцию-член для открытия HTTP-соединение.  
  
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
 Указатель на строку, содержащую целевого объекта указанной команды. Обычно это имя файла, исполняемым модулям или описатель поиска.  
  
 `pstrReferer`  
 Указатель на строку, указывающую адрес (URL) документа, из которого URL-адрес в запросе ( `pstrObjectName`) был получен. Если `NULL`, указан без заголовка HTTP.  
  
 `dwContext`  
 Идентификатор контекста для `OpenRequest` операции. См. в разделе "Примечания" Дополнительные сведения `dwContext`.  
  
 `ppstrAcceptTypes`  
 Указатель на завершающуюся нулевым значением из `LPCTSTR` указатели на строки, указывающее, типы содержимого, принятые клиентом. Если `ppstrAcceptTypes` — `NULL`, серверы интерпретировать клиент принимает только документы типа «текст / *» (то есть только текстовых документов и не рисунки или другие двоичные файлы). Тип содержимого будет соответствовать переменной указывается CGI, который определяет тип данных для запросов, которые были присоединены сведения, такие как HTTP POST и PUT.  
  
 `pstrVersion`  
 Указатель на строку, определяющую версию HTTP. Если `NULL`, используется «HTTP/1.0».  
  
 `dwFlags`  
 Любое сочетание флагов INTERNET_ FLAG_ *. См. в разделе "Примечания" Описание возможных `dwFlags` значения.  
  
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
|`INTERNET_FLAG_RELOAD`|Вызывает загрузку запрошенного файла, объекта или каталоге с основного сервера, а не из кэша.|  
|`INTERNET_FLAG_DONT_CACHE`|Не добавляет возвращаемой сущности в кэш.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|Добавляет в кэш возвращаемой сущности как постоянные сущность. Это означает, что очистка кэша standard, проверки согласованности или сборщик мусора не удается удалить этот элемент из кэша.|  
|`INTERNET_FLAG_SECURE`|Безопасный семантика транзакций. Это преобразует с помощью SSL или PCT и применяется только в HTTP-запросов|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|Используется только с HTTP, указывает, что перенаправления не должен обрабатываться автоматически в [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Переопределить `dwContext` по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста связан с этой определенной операции `CHttpConnection` объектом, созданным с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
 Исключения могут вызываться с помощью этой функции.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
