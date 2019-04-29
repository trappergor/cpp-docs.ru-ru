---
title: Класс CGopherConnection
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: d960d566a63531af211592a7a8ae8f1cb35c5958
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386279"
---
# <a name="cgopherconnection-class"></a>Класс CGopherConnection

Управление подключением к интернет-серверу gopher.

> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более ранние платформы.

## <a name="syntax"></a>Синтаксис

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Создает объект `CGopherConnection`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|Создает [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объект для поиска файлов на сервере gopher.|
|[CGopherConnection::GetAttribute](#getattribute)|Извлекает сведения об атрибутах об объекте gopher.|
|[CGopherConnection::OpenFile](#openfile)|Открывает файл gopher.|

## <a name="remarks"></a>Примечания

Служба gopher является одним из трех служб Интернета, распознаваемые классов MFC WinInet.

Класс `CGopherConnection` содержит три дополнительных функции-члена, которые управляют службы gopher и конструктора: [OpenFile](#openfile), [CreateLocator](#createlocator), и [GetAttribute](#getattribute).

Для взаимодействия с Интернет-серверу gopher, необходимо сначала создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем вызвать [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает `CGopherConnection` объект и возвращает указатель на него. Никогда не создаст `CGopherConnection` объекта напрямую.

Дополнительные сведения о том, как `CGopherConnection` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения об использовании двух других поддерживаемых служб Интернета, FTP и HTTP см. в разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection

Эта функция-член вызывается для создания `CGopherConnection` объекта.

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pSession*<br/>
Указатель на связанную [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.

*hConnected*<br/>
Дескриптор Windows текущего сеанса Интернет.

*pstrServer*<br/>
Указатель на строку, содержащую имя FTP-сервера.

*dwContext*<br/>
Идентификатор контекста для операции. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию имеет значение 1; Тем не менее можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связан с этим идентификатором контекста.

*pstrUserName*<br/>
Указатель на заканчивающуюся нулем строку, указывающее имя пользователя для входа. Если значение равно NULL, значение по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на заканчивающуюся нулем строку, указывающее пароль, используемый для входа. Если оба *pstrPassword* и *pstrUserName* имеют значение NULL, анонимные пароль по умолчанию — имя электронной почты пользователя. Если *pstrPassword* имеет значение NULL (или пустую строку), но *pstrUserName* не равно NULL, используется пустой пароль. В следующей таблице описаны поведение четыре возможные параметры *pstrUserName* и *pstrPassword*:

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправляемые серверу FTP|Пароля, передаваемых на FTP-сервер|
|--------------------|--------------------|---------------------------------|---------------------------------|
|Значение NULL или ""|Значение NULL или ""|«anonymous»|Имя электронной почты пользователя|
|НЕНУЛЕВЫЕ строковые|Значение NULL или ""|*pstrUserName*|" "|
|NULL НЕПУСТАЯ строка|ОШИБКА|ОШИБКА||
|НЕНУЛЕВЫЕ строковые|НЕНУЛЕВЫЕ строковые|*pstrUserName*|*pstrPassword*|

*nPort*<br/>
Число, идентифицирующее порт TCP/IP, используемый на сервере.

### <a name="remarks"></a>Примечания

Никогда не создаст `CGopherConnection` напрямую. Вместо этого вызовите [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает `CGopherConnection` объекта и возвращает указатель на него.

##  <a name="createlocator"></a>  CGopherConnection::CreateLocator

Вызывайте эту функцию член, чтобы создать указатель gopher для поиска или определения файла на сервере gopher.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pstrDisplayString*<br/>
Указатель на строку, содержащую имя gopher документа или папки должны быть получены. Если *pstrDisplayString* параметр равен NULL, возвращается каталог по умолчанию для сервера gopher.

*pstrSelectorString*<br/>
Указатель на строка селектора, которые нужно отправить на сервер gopher для извлечения объекта. *pstrSelectorString* может иметь значение NULL.

*dwGopherType*<br/>
Этот параметр указывает ли *pstrSelectorString* ссылается на каталог или документа, и является ли запрос gopher или gopher +. Просмотреть атрибуты для структуры [GOPHER_FIND_DATA](/windows/desktop/api/wininet/ns-wininet-gopher_find_dataa) в пакете Windows SDK.

*pstrLocator*<br/>
Указатель на строку, определяющую нужный файл. Как правило, эта строка возвращается из вызова [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*pstrServerName*<br/>
Указатель на строку, содержащую имя сервера gopher.

*nPort*<br/>
Номер, идентифицирующий Интернет порт для этого подключения.

### <a name="return-value"></a>Возвращаемое значение

Объект [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.

### <a name="remarks"></a>Примечания

Статическая версия функции-члена необходимо указать сервер, пока в нестатических версии используется имя сервера из объекта соединения.

Чтобы получить сведения с сервера gopher, приложение сначала необходимо получить указатель gopher. Приложение должно затем обрабатывать указателя как непрозрачный маркер (т. е приложение может использовать указателя, но не напрямую манипулировать или сравнить его). Как правило, приложение использует средство поиска для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) функция-член для извлечения определенной части сведения.

##  <a name="getattribute"></a>  CGopherConnection::GetAttribute

Вызовите эту функцию-член для получения конкретного атрибута сведений об элементе с сервера gopher.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Параметры

*refLocator*<br/>
Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.

*strRequestedAttributes*<br/>
Строка с разделителями пробелами, указания имен атрибутов.

*strResult*<br/>
Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , получающий тип указателя.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

##  <a name="openfile"></a>  CGopherConnection::OpenFile

Вызов этой функции-члена для открытия файла на сервере gopher.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*refLocator*<br/>
Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.

*dwFlags*<br/>
Любое сочетание флагов INTERNET_FLAG_ *. См. в разделе [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) для получения дополнительных сведений о INTERNET_FLAG_\* флаги.

*pstrView*<br/>
Указатель на строковое представление файлов. Если на сервере существует несколько представлений для файла, этот параметр указывает, какое представление файла, чтобы открыть. Если *pstrView* имеет значение NULL, используется представление файлов по умолчанию.

*dwContext*<br/>
Идентификатор контекста для открываемого файла. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CGopherFile](../../mfc/reference/cgopherfile-class.md) объекта должны быть открыты.

### <a name="remarks"></a>Примечания

Переопределить *dwContext* по умолчанию для задания идентификатора контекста в значение по своему выбору. Идентификатор контекста связан с этой конкретной операции из `CGopherConnection` объект, созданный с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение для [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

## <a name="see-also"></a>См. также

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
