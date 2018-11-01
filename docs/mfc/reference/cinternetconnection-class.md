---
title: Класс CInternetConnection
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: da11f62cfb453e31d3cacc1d4bc5b8a26f5b3764
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564805"
---
# <a name="cinternetconnection-class"></a>Класс CInternetConnection

Управление подключением к интернет-серверу.

## <a name="syntax"></a>Синтаксис

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Создает объект `CInternetConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|Получает идентификатор контекста для данного объекта подключения.|
|[CInternetConnection::GetServerName](#getservername)|Возвращает имя сервера, связанного с соединением.|
|[CInternetConnection::GetSession](#getsession)|Возвращает указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объект, связанный с соединением.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Дескриптор для Интернет-сеанс.|

## <a name="remarks"></a>Примечания

Это базовый класс для классов MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Каждый из этих классов предоставляет дополнительные функциональные возможности для взаимодействия с на соответствующий сервер FTP, HTTP или gopher.

Для взаимодействия непосредственно с веб-сервером, необходимо иметь [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта и `CInternetConnection` объекта.

Дополнительные сведения о как WinInet классов, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection

Эта функция-член вызывается, когда `CInternetConnection` создается объект.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pSession*<br/>
Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*nPort*<br/>
Число, идентифицирующее порт Интернета для этого подключения.

*dwContext*<br/>
Идентификатор контекста для `CInternetConnection` объекта. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="remarks"></a>Примечания

Никогда не вызовет `CInternetConnection` самостоятельно; вместо этого необходимо вызвать [CInternetSession](../../mfc/reference/cinternetsession-class.md) функция-член для типа соединения, которым требуется установить:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

Значение по умолчанию для *dwContext* отправленные MFC для `CInternetConnection`-производный объект от [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан **Интернет-соединение**- производный объект. Значение по умолчанию имеет значение 1; Тем не менее, можно явно назначить идентификатором контекста в [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) конструктор для соединения. Объект, а вся работа, она будет связан с этим идентификатором контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния в объекте, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="getcontext"></a>  CInternetConnection::GetContext

Вызывайте эту функцию члена, чтобы получить идентификатор контекста для этого сеанса.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор контекста, назначенные приложению

### <a name="remarks"></a>Примечания

Идентификатор контекста изначально указывается в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и распространение на `CInternetConnection`- и [CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы, в том случае, если не указано иное, в вызове функции, которая открывает подключение. Идентификатор контекста связан с любой операции данного объекта и определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

Дополнительные сведения о том, как `GetContext` работает с другими классами WinInet, чтобы предоставить сведения о состоянии пользователя, см. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="getservername"></a>  CInternetConnection::GetServerName

Вызов для получения имени сервера, связанного с этим подключением Интернета эта функция-член.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя сервера, внутри которого работает данный объект подключения.

##  <a name="getsession"></a>  CInternetConnection::GetSession

Вызов этой функции-члена для получения указателя на `CInternetSession` объект, который связан с этим подключением.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объект, связанный с данным объектом подключения Интернет.

##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET

Этот оператор используется для получения дескриптора уровень API для текущего сеанса Internet.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

