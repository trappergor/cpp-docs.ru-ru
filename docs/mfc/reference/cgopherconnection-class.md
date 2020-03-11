---
title: Класс Кгоферконнектион
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
ms.openlocfilehash: f5d655aa7fd2eb9e41c15c60a71492c24ba43c43
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883906"
---
# <a name="cgopherconnection-class"></a>Класс Кгоферконнектион

Управление подключением к интернет-серверу gopher.

> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они продолжат работать на более ранних платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кгоферконнектион:: Кгоферконнектион](#cgopherconnection)|Формирует объект `CGopherConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кгоферконнектион:: CreateLocator](#createlocator)|Создает объект [кгоферлокатор](../../mfc/reference/cgopherlocator-class.md) для поиска файлов на сервере Gopher.|
|[Кгоферконнектион:: OutAttribute](#getattribute)|Извлекает сведения об атрибутах для объекта Gopher.|
|[Кгоферконнектион:: OpenFile](#openfile)|Открывает файл gopher.|

## <a name="remarks"></a>Remarks

Служба Gopher — одна из трех служб Интернета, распознаваемых классами MFC WinInet.

Класс `CGopherConnection` содержит конструктор и три дополнительные функции-члены, управляющие службой gopher: [OpenFile](#openfile), [CreateLocator](#createlocator)и [OutAttribute](#getattribute).

Для взаимодействия с Интернет-сервером Gopher необходимо сначала создать экземпляр [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md), а затем вызвать [Цинтернетсессион:: жетгоферконнектион](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает объект `CGopherConnection` и возвращает указатель на него. Вы никогда не создаете объект `CGopherConnection` напрямую.

Дополнительные сведения о том, как `CGopherConnection` работает с другими классами Интернета MFC, см. в статье [программирование через Интернет с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения об использовании двух других поддерживаемых служб Интернета, FTP и HTTP см. в разделе Классы [чттпконнектион](../../mfc/reference/chttpconnection-class.md) и [кфтпконнектион](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[Цинтернетконнектион](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет. h

##  <a name="cgopherconnection"></a>Кгоферконнектион:: Кгоферконнектион

Эта функция-член вызывается для создания объекта `CGopherConnection`.

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

*псессион*<br/>
Указатель на связанный объект [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) .

*хконнектед*<br/>
Маркер текущего сеанса Интернета в Windows.

*пстрсервер*<br/>
Указатель на строку, содержащую имя FTP-сервера.

*двконтекст*<br/>
Идентификатор контекста для операции. *двконтекст* определяет сведения о состоянии операции, возвращаемые [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию — 1; Однако для операции можно явно назначить конкретный идентификатор контекста. Объект и все его работа будут связаны с ИДЕНТИФИКАТОРом контекста.

*пструсернаме*<br/>
Указатель на строку, завершающуюся нулем, которая указывает имя пользователя для входа. Если значение равно NULL, значение по умолчанию — Anonymous.

*пстрпассворд*<br/>
Указатель на строку, завершающуюся нулем, которая указывает пароль, используемый для входа в систему. Если оба *пстрпассворд* и *пструсернаме* имеют значение null, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *пстрпассворд* имеет значение null (или пустая строка), но *пструсернаме* не имеет значение null, используется пустой пароль. В следующей таблице описывается поведение четырех возможных параметров *пструсернаме* и *пстрпассворд*.

|*пструсернаме*|*пстрпассворд*|Имя пользователя, отправленное на FTP-сервер|Пароль, отправленный на FTP-сервер|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL или ""|NULL или ""|подключившихся|Имя электронной почты пользователя|
|Строка, не РАВНая NULL|NULL или ""|*пструсернаме*|" "|
|Строка со значением NULL, отличным от NULL|ошибка|ошибка||
|Строка, не РАВНая NULL|Строка, не РАВНая NULL|*пструсернаме*|*пстрпассворд*|

*Nпорт*<br/>
Число, идентифицирующее порт TCP/IP, используемый на сервере.

### <a name="remarks"></a>Remarks

Вы никогда не создаете `CGopherConnection` напрямую. Вместо этого вызовите [Цинтернетсессион:: жетгоферконнектион](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает объект `CGopherConnection` и возвращает указатель на него.

##  <a name="createlocator"></a>Кгоферконнектион:: CreateLocator

Вызовите эту функцию-член, чтобы создать локатор gopher для поиска или определения файла на сервере Gopher.

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

*пстрдисплайстринг*<br/>
Указатель на строку, содержащую имя документа или каталога Gopher, который требуется получить. Если параметр *пстрдисплайстринг* имеет значение null, возвращается каталог по умолчанию для сервера gopher.

*пстрселекторстринг*<br/>
Указатель на строку селектора, которая будет отправлена на сервер gopher для получения элемента. *пстрселекторстринг* может иметь значение null.

*двгофертипе*<br/>
Указывает, относится ли *пстрселекторстринг* к каталогу или документу и является ли запрос Gopher или gopher +. См. атрибуты [GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw) структуры в Windows SDK.

*пстрлокатор*<br/>
Указатель на строку, идентифицирующую открываемый файл. Как правило, эта строка возвращается из вызова [кгоферфилефинд::-Locator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*пстрсервернаме*<br/>
Указатель на строку, содержащую имя сервера gopher.

*Nпорт*<br/>
Номер, определяющий порт Интернета для данного подключения.

### <a name="return-value"></a>Возвращаемое значение

Объект [кгоферлокатор](../../mfc/reference/cgopherlocator-class.md) .

### <a name="remarks"></a>Remarks

Статическая версия функции-члена требует указать сервер, а нестатическая версия использует имя сервера из объекта соединения.

Чтобы получить сведения с сервера gopher, приложение должно сначала получить локатор Gopher. Приложение должно обрабатывать указатель как непрозрачный маркер (т. е. приложение может использовать указатель, но не обрабатывает его напрямую или сравнивать его). Как правило, приложение использует локатор для вызовов функции-члена [кгоферфилефинд:: финдфиле](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения определенного фрагмента информации.

##  <a name="getattribute"></a>Кгоферконнектион:: OutAttribute

Вызовите эту функцию члена, чтобы получить сведения об определенном атрибуте элемента с сервера gopher.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Параметры

*рефлокатор*<br/>
Ссылка на объект [кгоферлокатор](../../mfc/reference/cgopherlocator-class.md) .

*стррекуестедаттрибутес*<br/>
Строка с разделителями-пробелами, указывающая имена запрошенных атрибутов.

*стрресулт*<br/>
Ссылка на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , принимающая тип указателя.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается неудачно, можно вызвать функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) , чтобы определить причину ошибки.

##  <a name="openfile"></a>Кгоферконнектион:: OpenFile

Вызовите эту функцию-член, чтобы открыть файл на сервере Gopher.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*рефлокатор*<br/>
Ссылка на объект [кгоферлокатор](../../mfc/reference/cgopherlocator-class.md) .

*dwFlags*<br/>
Любое сочетание флагов INTERNET_FLAG_ *. Дополнительные сведения о INTERNET_FLAG_\*ных флагах см. в разделе [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) .

*пстрвиев*<br/>
Указатель на строку представления файла. Если на сервере существует несколько представлений файла, этот параметр указывает, какое представление файла следует открыть. Если *пстрвиев* имеет значение null, используется представление файла по умолчанию.

*двконтекст*<br/>
Идентификатор контекста для открываемого файла. Дополнительные сведения о *двконтекст*см. в разделе **Примечания** .

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CGopherFile](../../mfc/reference/cgopherfile-class.md) , который нужно открыть.

### <a name="remarks"></a>Remarks

Переопределите *двконтекст* по умолчанию, чтобы задать для идентификатора контекста значение, выбранное вами. Идентификатор контекста связан с этой конкретной операцией объекта `CGopherConnection`, созданного его объектом [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) . Значение возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние операции, с которой оно определено. Дополнительные сведения об идентификаторе контекста см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) .

## <a name="see-also"></a>См. также раздел

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
