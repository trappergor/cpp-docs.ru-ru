---
title: Класс CHttpConnection
ms.date: 03/27/2019
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: 1941af1e16a897235dd90db509d6ed29c2d9a875
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565260"
---
# <a name="chttpconnection-class"></a>Класс CHttpConnection

Управление подключением к HTTP-серверу.

## <a name="syntax"></a>Синтаксис

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CHttpConnection::CHttpConnection](#chttpconnection)|Создает объект `CHttpConnection`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|Открывает HTTP-запроса.|

## <a name="remarks"></a>Примечания

HTTP — один из трех протоколов сервера Интернета, реализованы с помощью классов MFC WinInet.

Класс `CHttpConnection` содержит конструктор и функции-члена одного [OpenRequest](#openrequest), управляющий подключений к серверу с протоколом HTTP.

Для взаимодействия с HTTP-сервера, необходимо сначала создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создайте [CHttpConnection](#chttpconnection) объекта. Никогда не создаст `CHttpConnection` объекта напрямую; вместо этого вызовите [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), который создает `CHttpConnection` объекта и возвращает указатель на него.

Дополнительные сведения о том, как `CHttpConnection` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о подключении к серверам, используя две другие поддерживаемые протоколы Интернета, gopher и FTP, см. в разделе классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="chttpconnection"></a>  CHttpConnection::CHttpConnection

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

*pSession*<br/>
Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.

*hConnected*<br/>
Дескриптор подключения к Интернету.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*dwContext*<br/>
Идентификатор контекста для `CInternetConnection` объекта. Дополнительные сведения о *dwContext*, см. в разделе **"Примечания"** раздел.

*nPort*<br/>
Число, идентифицирующее порт Интернета для этого подключения.

*pstrUserName*<br/>
Указатель на заканчивающуюся нулем строку, указывающее имя пользователя для входа. Если значение равно NULL, значение по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на заканчивающуюся нулем строку, указывающее пароль, используемый для входа. Если оба *pstrPassword* и *pstrUserName* имеют значение NULL, анонимные пароль по умолчанию — имя электронной почты пользователя. Если *pstrPassword* имеет значение NULL или является пустой строкой, но *pstrUserName* не равно NULL, используется пустой пароль. В следующей таблице описаны поведение четыре возможные параметры *pstrUserName* и *pstrPassword*:

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправляемые серверу FTP|Пароля, передаваемых на FTP-сервер|
|--------------------|--------------------|---------------------------------|---------------------------------|
|Значение NULL или ""|Значение NULL или ""|«anonymous»|Имя электронной почты пользователя|
|НЕНУЛЕВЫЕ строковые|Значение NULL или ""|*pstrUserName*|" "|
|NULL |НЕНУЛЕВЫЕ строковые|ОШИБКА|ОШИБКА|
|НЕНУЛЕВЫЕ строковые|НЕНУЛЕВЫЕ строковые|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
Любое сочетание `INTERNET_FLAG_*` флаги. См. в таблице в **"Примечания"** раздел [CHttpConnection::OpenRequest](#openrequest) описание *dwFlags* значения.

### <a name="remarks"></a>Примечания

Никогда не создаст `CHttpConnection` напрямую. Вместо этого вы создаете объект, вызвав [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

##  <a name="openrequest"></a>  CHttpConnection::OpenRequest

Вызывайте эту функцию члена, чтобы открыть подключение HTTP.

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

*pstrVerb*<br/>
Указатель на строку, содержащую команду, используемую в запросе. Если значение равно NULL, используется «GET».

*pstrObjectName*<br/>
Указатель на строку, содержащую целевой объект указанную команду. Эта строка обычно является имя файла, исполняемый модуль или описатель поиска.

*pstrReferer*<br/>
Указатель на строку, которая указывает URL-адрес документа, из которого URL-адрес в запросе (*pstrObjectName*) был получен. Если значение равно NULL, указан без заголовка HTTP.

*dwContext*<br/>
Идентификатор контекста для `OpenRequest` операции. Дополнительные сведения о *dwContext*, см. в разделе "Примечания".

*ppstrAcceptTypes*<br/>
Указатель на указатели LPCTSTR для строк, обозначающих типы содержимого, принятый клиентом, завершающуюся нулевым значением. Если *ppstrAcceptTypes* имеет значение NULL, серверы интерпретации, что клиент принимает только документов типа «text / *» (то есть только текстовых документов и не рисунки или другие двоичные файлы). Тип содержимого является эквивалентом переменных CONTENT_TYPE CGI, который определяет тип данных для запросов, которые были присоединены сведения, такие как HTTP POST и PUT.

*pstrVersion*<br/>
Указатель на строку, определяющую версию HTTP. Если значение равно NULL, используется «HTTP/1.0».

*dwFlags*<br/>
Любое сочетание флагов INTERNET_ FLAG_ *. См. в разделе "Примечания" Описание возможных *dwFlags* значения.

*nVerb*<br/>
Номер, связанный с типом запроса HTTP. Ниже указаны доступные значения.

|Тип HTTP-запроса|*nVerb* значение|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CHttpFile](../../mfc/reference/chttpfile-class.md) запрошенный объект.

### <a name="remarks"></a>Примечания

*dwFlags* может принимать одно из следующих:

|Флаг Internet|Описание|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|Вызывает загрузку запрошенного файла, объекта или списка каталогов с сервера-источника, а не из кэша.|
|INTERNET_FLAG_DONT_CACHE|Не добавляет сущность, возвращаемую в кэш.|
|INTERNET_FLAG_MAKE_PERSISTENT|Добавляет сущность, возвращаемую в кэш как постоянные сущность. Это означает, что очистка кэша standard, проверки согласованности или сбора мусора не удается удалить этот элемент из кэша.|
|INTERNET_FLAG_SECURE|Использует безопасные семантика транзакций. Он преобразуется с помощью SSL/PCT и применяется только в HTTP-запросов|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Используется только с HTTP, указывает, что перенаправления не должны обрабатываться автоматически в [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Переопределить `dwContext` по умолчанию для задания идентификатора контекста в значение по своему выбору. Идентификатор контекста связан с этой конкретной операции из `CHttpConnection` объект, созданный с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение для [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

Исключения могут вызываться с помощью этой функции.

## <a name="see-also"></a>См. также

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
