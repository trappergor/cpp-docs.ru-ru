---
title: Класс Чттпконнектион
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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425895"
---
# <a name="chttpconnection-class"></a>Класс Чттпконнектион

Управление подключением к HTTP-серверу.

## <a name="syntax"></a>Синтаксис

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Чттпконнектион:: Чттпконнектион](#chttpconnection)|Создает объект `CHttpConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Чттпконнектион:: Опенрекуест](#openrequest)|Открывает HTTP-запрос.|

## <a name="remarks"></a>Remarks

HTTP — один из трех протоколов Интернет-сервера, реализованных классами MFC WinInet.

Класс `CHttpConnection` содержит конструктор и одну функцию-член [опенрекуест](#openrequest), которая управляет соединениями с сервером по протоколу HTTP.

Для взаимодействия с сервером HTTP необходимо сначала создать экземпляр [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md), а затем создать объект [чттпконнектион](#chttpconnection) . Вы никогда не создаете объект `CHttpConnection` напрямую; Вместо этого вызовите [Цинтернетсессион:: жесттпконнектион](../../mfc/reference/cinternetsession-class.md#gethttpconnection), который создает объект `CHttpConnection` и возвращает указатель на него.

Дополнительные сведения о том, как `CHttpConnection` работает с другими классами Интернета MFC, см. в статье [программирование через Интернет с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о подключении к серверам с помощью двух других поддерживаемых протоколов Интернета, Gopher и FTP см. в разделе Классы [кгоферконнектион](../../mfc/reference/cgopherconnection-class.md) и [кфтпконнектион](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[Цинтернетконнектион](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет. h

##  <a name="chttpconnection"></a>Чттпконнектион:: Чттпконнектион

Эта функция-член вызывается для создания объекта `CHttpConnection`.

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

*псессион*<br/>
Указатель на объект [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) .

*хконнектед*<br/>
Маркер подключения к Интернету.

*пстрсервер*<br/>
Указатель на строку, содержащую имя сервера.

*двконтекст*<br/>
Идентификатор контекста для объекта `CInternetConnection`. Дополнительные сведения о *двконтекст*см. в разделе **"Примечания** ".

*Nпорт*<br/>
Номер, определяющий порт Интернета для данного соединения.

*пструсернаме*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя пользователя для входа. Если значение равно NULL, значение по умолчанию — Anonymous.

*пстрпассворд*<br/>
Указатель на строку, завершающуюся нулем, которая указывает пароль, используемый для входа. Если оба *пстрпассворд* и *пструсернаме* имеют значение null, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *пстрпассворд* имеет значение null или является пустой строкой, но *ПСТРУСЕРНАМЕ* не равен null, используется пустой пароль. В следующей таблице описывается поведение четырех возможных параметров *пструсернаме* и *пстрпассворд*.

|*пструсернаме*|*пстрпассворд*|Имя пользователя, отправленное на FTP-сервер|Пароль, отправленный на FTP-сервер|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL или ""|NULL или ""|подключившихся|Имя электронной почты пользователя|
|Строка, не РАВНая NULL|NULL или ""|*пструсернаме*|" "|
|NULL |Строка, не РАВНая NULL|ошибка|ошибка|
|Строка, не РАВНая NULL|Строка, не РАВНая NULL|*пструсернаме*|*пстрпассворд*|

*dwFlags*<br/>
Любое сочетание флагов `INTERNET_FLAG_*`. Описание значений *dwFlags* см. в таблице в разделе **"Примечания"** раздела [чттпконнектион:: опенрекуест](#openrequest) .

### <a name="remarks"></a>Remarks

Вы никогда не создаете `CHttpConnection` напрямую. Вместо этого создайте объект, вызвав [Цинтернетсессион:: жесттпконнектион](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

##  <a name="openrequest"></a>Чттпконнектион:: Опенрекуест

Вызовите эту функцию-член, чтобы открыть соединение по протоколу HTTP.

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

*пстрверб*<br/>
Указатель на строку, содержащую команду, используемую в запросе. Если значение равно NULL, используется "GET".

*пстробжектнаме*<br/>
Указатель на строку, содержащую целевой объект указанной команды. Эта строка обычно представляет собой имя файла, исполняемый модуль или описатель поиска.

*пстрреферер*<br/>
Указатель на строку, указывающую адрес (URL) документа, из которого был получен URL-адрес в запросе (*пстробжектнаме*). Если значение равно NULL, заголовок HTTP не указан.

*двконтекст*<br/>
Идентификатор контекста для операции `OpenRequest`. Дополнительные сведения о *двконтекст*см. в разделе "Примечания".

*ппстракцепттипес*<br/>
Указатель на массив LPCTSTR указателей, заканчивающийся нулем, на строки, указывающие типы содержимого, принимаемые клиентом. Если *ппстракцепттипес* имеет значение null, серверы распознает, что клиент принимает только документы типа "Text/*" (то есть только текстовые документы, а не рисунки и другие двоичные файлы). Тип содержимого эквивалентен переменной CGI CONTENT_TYPE, которая определяет тип данных для запросов с присоединенными сведениями, таких как HTTP POST и постановка.

*пстрверсион*<br/>
Указатель на строку, определяющую версию HTTP. Если задано значение NULL, используется "HTTP/1.0".

*dwFlags*<br/>
Любое сочетание флагов INTERNET_ FLAG_ *. Описание возможных значений *dwFlags* см. в разделе "Примечания".

*нверб*<br/>
Число, связанное с типом HTTP-запроса. Может применяться один из перечисленных ниже типов.

|Тип HTTP-запроса|значение *нверб*|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Возвращаемое значение

Запрошенный указатель на объект [чттпфиле](../../mfc/reference/chttpfile-class.md) .

### <a name="remarks"></a>Remarks

*dwFlags* может быть одним из следующих:

|Флаг Интернета|Description|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|Принудительно загружает запрошенный файл, объект или каталог с сервера-источника, а не из кэша.|
|INTERNET_FLAG_DONT_CACHE|Не добавляет возвращенную сущность в кэш.|
|INTERNET_FLAG_MAKE_PERSISTENT|Добавляет возвращенную сущность в кэш как постоянную сущность. Это означает, что стандартная очистка кэша, проверка согласованности или сбор мусора не могут удалить этот элемент из кэша.|
|INTERNET_FLAG_SECURE|Использует безопасную семантику транзакций. Он преобразуется в использование SSL/PCT и имеет смысл только в HTTP-запросах.|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Используется только с HTTP, указывает, что перенаправления не должны обрабатываться автоматически в [чттпфиле:: SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Переопределите `dwContext` умолчанию, чтобы задать для идентификатора контекста значение, выбранное вами. Идентификатор контекста связан с этой конкретной операцией объекта `CHttpConnection`, созданного его объектом [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) . Значение возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние операции, с которой оно определено. Дополнительные сведения об идентификаторе контекста см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) .

С этой функцией могут возникать исключения.

## <a name="see-also"></a>См. также раздел

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CHttpFile](../../mfc/reference/chttpfile-class.md)
