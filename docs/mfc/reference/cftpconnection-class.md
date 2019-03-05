---
title: Класс CFtpConnection
ms.date: 11/04/2016
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
ms.openlocfilehash: 12ef4de16279c5c2033a95df5928a6dfb7a2a652
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295127"
---
# <a name="cftpconnection-class"></a>Класс CFtpConnection

Управление подключением к Интернет-серверу FTP и позволяет напрямую управлять каталоги и файлы на этом сервере.

## <a name="syntax"></a>Синтаксис

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CFtpConnection::CFtpConnection](#cftpconnection)|Создает объект `CFtpConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CFtpConnection::Command](#command)|Отправляет команду напрямую на FTP-сервер.|
|[CFtpConnection::CreateDirectory](#createdirectory)|Создает каталог на сервере.|
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Возвращает текущий каталог для этого подключения.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Возвращает текущий каталог для этого подключения, URL-адрес.|
|[CFtpConnection::GetFile](#getfile)|Получает файл из подключенного сервера|
|[CFtpConnection::OpenFile](#openfile)|Открывает файл на подключенном сервере.|
|[CFtpConnection::PutFile](#putfile)|Помещает файл на сервере.|
|[CFtpConnection::Remove](#remove)|Удаляет файл с сервера.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|Удаляет указанный каталог с сервера.|
|[CFtpConnection::Rename](#rename)|Переименовывает файл на сервере.|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Задает текущий каталог FTP.|

## <a name="remarks"></a>Примечания

FTP является одним из трех служб Интернета, распознаваемые классов MFC WinInet.

Для взаимодействия с FTP веб-сервером, необходимо сначала создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создайте `CFtpConnection` объекта. Никогда не создаст `CFtpConnection` объекта напрямую; вместо этого вызовите [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает `CFtpConnection` объекта и возвращает указатель на него.

Дополнительные сведения о том, как `CFtpConnection` работает с другими классами MFC Интернет, см. в статье [Internet программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о взаимодействии с двумя другими поддерживаемые службы, HTTP и gopher, см. в разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).

## <a name="example"></a>Пример

  Ознакомьтесь с примером в [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Общие сведения о классе.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection

Эта функция-член вызывается для создания `CFtpConnection` объекта.

```
CFtpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CFtpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
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

*bPassive*<br/>
Задает пассивный или активный режим для этого сеанса FTP. Если задано значение TRUE, то он устанавливает Win32 API *dwFlag* для INTERNET_FLAG_PASSIVE.

### <a name="remarks"></a>Примечания

Никогда не создаст `CFtpConnection` объекта напрямую. Вместо этого необходимо вызвать [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает `CFptConnection` объекта.

##  <a name="command"></a>  CFtpConnection::Command

Отправляет команду напрямую на FTP-сервер.

```
CInternetFile* Command(
    LPCTSTR pszCommand,
    CmdResponseType eResponse = CmdRespNone,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pszCommand*<br/>
Указатель на строку, содержащую отправляемую команду.

*eResponse*<br/>
Определяет, следует ли ожидать ответ FTP-сервера. Может принимать одно из следующих значений:

- `CmdRespNone` Ответ не ожидается.

- `CmdRespRead` Ожидается ответ.

*dwFlags*<br/>
Значение, содержащее флаги, управляющие этой функцией. Полный список см. в разделе [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda).

*dwContext*<br/>
Указатель на значение, содержащее определяемое приложением значение, используемое для идентификации контекста приложения в обратных вызовах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член эмулирует функциональные возможности [FTPCommand](/windows/desktop/api/wininet/nf-wininet-ftpcommanda) функции, как описано в пакете Windows SDK.

В случае ошибки MFC вызывает исключение типа [CInternetException](../../mfc/reference/cinternetexception-class.md).

##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory

Вызывайте эту функцию члена, чтобы создать каталог на подключенном сервере.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель на строку, содержащую имя каталога для создания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов завершается ошибкой, функция Windows [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте `GetCurrentDirectory` для определения текущего рабочего каталога для этого подключения к серверу. Не следует предполагать, что удаленная система подключился вы к корневому каталогу.

`pstrDirName` Параметр может быть либо частично или полное имя файла, относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `CreateDirectory` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="getcurrentdirectory"></a>  CFtpConnection::GetCurrentDirectory

Вызывайте эту функцию члена, чтобы получить имя текущего каталога.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Параметры

*strDirName*<br/>
Ссылка на строку, которая будет принимать имя каталога.

*pstrDirName*<br/>
Указатель на строку, которая будет принимать имя каталога.

*lpdwLen*<br/>
Указатель на значение DWORD, содержащее следующие сведения:

|||
|-|-|
|При входе|Размер буфера, который ссылается *pstrDirName*.|
|При возврате|Число символов, сохраненных для *pstrDirName*. Если функция-член, происходит сбой, и возвращается значение ERROR_INSUFFICIENT_BUFFER, затем *lpdwLen* содержит число байтов, которые приложение должно выделить для получения строки.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Чтобы получить имя каталога как URL-адрес, вызовите [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).

Параметры *pstrDirName* или *strDirName* может быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetCurrentDirectory` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL

Вызывайте эту функцию члена, чтобы получить имя текущего каталога как URL-адрес.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Параметры

*strDirName*<br/>
Ссылка на строку, которая будет принимать имя каталога.

*pstrDirName*<br/>
Указатель на строку, которая будет принимать имя каталога.

*lpdwLen*<br/>
Указатель на значение DWORD, содержащее следующие сведения:

|||
|-|-|
|При входе|Размер буфера, который ссылается *pstrDirName*.|
|При возврате|Число символов, сохраненных для *pstrDirName*. Если функция-член, происходит сбой, и возвращается значение ERROR_INSUFFICIENT_BUFFER, затем *lpdwLen* содержит число байтов, которые приложение должно выделить для получения строки.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

`GetCurrentDirectoryAsURL` ведет себя так же, как [GetCurrentDirectory](#getcurrentdirectory)

Параметр *strDirName* может быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetCurrentDirectoryAsURL` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="getfile"></a>  CFtpConnection::GetFile

Вызов этой функции-члена для получения файла от FTP-сервера и сохранить его на локальном компьютере.

```
BOOL GetFile(
    LPCTSTR pstrRemoteFile,
    LPCTSTR pstrLocalFile,
    BOOL bFailIfExists = TRUE,
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pstrRemoteFile*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя файла для извлечения из FTP-сервера.

*pstrLocalFile*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя файла для создания в локальной системе.

*bFailIfExists*<br/>
Указывает ли имя файла может быть использован уже существующего файла. Если имя локального файла уже существует, и этот параметр имеет значение TRUE, `GetFile` завершается ошибкой. В противном случае `GetFile` приведет к удалению существующих копия файла.

*dwAttributes*<br/>
Указывает атрибуты файла. Это может быть любое сочетание следующих флагов FILE_ATTRIBUTE_ *.

- FILE_ATTRIBUTE_ARCHIVE файл представляет собой файл архива. Приложения используют этот атрибут для пометки файлов для резервного копирования или удаления.

- Сжимается FILE_ATTRIBUTE_COMPRESSED файлу или каталогу. Для файла сжатие означает, что все данные в файле сжата. Для каталога Сжатие по умолчанию для вновь создаваемых файлов и подкаталогов.

- FILE_ATTRIBUTE_DIRECTORY файл является каталогом.

- FILE_ATTRIBUTE_NORMAL файл имеет другие атрибуты не установлены. Этот атрибут действителен только в том случае, если используется отдельно. Все другие атрибуты файла переопределить FILE_ATTRIBUTE_NORMAL:

- FILE_ATTRIBUTE_HIDDEN файл является скрытым. Это не должны быть включены в обычный список каталога.

- FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но нельзя записывать данные в него или удалите его.

- FILE_ATTRIBUTE_SYSTEM файл является частью, или используется исключительно операционной системой.

- FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Приложения следует записать в файл только в том случае, если это абсолютно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл скоро будет удален.

*dwFlags*<br/>
Определяет условия, при которых происходит передача. Этот параметр может иметь любой из *dwFlags* значений описано в разделе [FtpGetFile](/windows/desktop/api/wininet/nf-wininet-ftpgetfilea) в пакете Windows SDK.

*dwContext*<br/>
Идентификатор контекста для получения файла. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

`GetFile` — Это высокоуровневый подпрограмму, которая обрабатывает все дополнительные издержки, связанные с считывания файла из FTP-сервере и сохранив его локально. Приложения, только для извлечения файла данных или для которых потребуется закрыть контролировать передачу файла, должны использовать `OpenFile` и [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) вместо этого.

Если *dwFlags* FILE_TRANSFER_TYPE_ASCII перевода данных файлов также преобразует управления и форматирование символов в Windows эквиваленты. Передача по умолчанию является двоичный режим, где файл загружается в тот же формат, так как оно хранится на сервере.

Оба *pstrRemoteFile* и *pstrLocalFile* может быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetFile` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

Переопределить *dwContext* по умолчанию для задания идентификатора контекста в значение по своему выбору. Идентификатор контекста связан с этой конкретной операции из `CFtpConnection` объект, созданный с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение для [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="openfile"></a>  CFtpConnection::OpenFile

Вызов этой функции-члена для открытия файла на FTP-сервера для чтения или записи.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pstrFileName*<br/>
Указатель на строку, содержащую имя файла для открытия.

*dwAccess*<br/>
Определяет, как доступ к файлу. Может быть GENERIC_READ или GENERIC_WRITE, но не оба.

*dwFlags*<br/>
Определяет условия, при которых последующих перенос. Это может быть любой из следующих констант FTP_TRANSFER_ *:

- FTP_TRANSFER_TYPE_ASCII файл передает с помощью метода передачи FTP ASCII (тип A). Преобразует элемент управления и сведения о форматировании в локальные эквиваленты.

- FTP_TRANSFER_TYPE_BINARY файл передает данные с использованием метода передачи образа FTP's (тип I). Передача файлов данных точно так, как он существует, без изменений. Это метод передачи по умолчанию.

*dwContext*<br/>
Идентификатор контекста для открытия файла. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на [CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта.

### <a name="remarks"></a>Примечания

`OpenFile` следует использовать в следующих ситуациях:

- Приложение имеет данные, которые должны быть отправлено и создан в виде файла на FTP-сервера, но, что данные не в локальном файле. Один раз `OpenFile` открывает файл, приложение использует [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) для отправки данных FTP файл на сервер.

- Приложения должны получить файл с сервера и поместите его в память, управляемые приложения, вместо записи на диск. Приложение использует [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) после использования `OpenFile` для открытия файла.

- Приложению требуется точный контроль над передачи файла. Например, приложению может понадобиться отображения индикатора выполнения элемента управления отображения хода состояние передачи файлов при загрузке файла.

После вызова метода `OpenFile` и до вызова метода `CInternetConnection::Close`, приложение может вызывать только [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`, или [ CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Для вызовов других функций FTP для одного сеанса FTP, завершатся неудачей и будут присвоено FTP_ETRANSFER_IN_PROGRESS код ошибки.

*PstrFileName* параметр может быть либо частично определенное имя файла в текущий каталог относительный или полный путь. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `OpenFile` Преобразует имя разделителей каталогов в соответствующие символы перед его использованием.

Переопределить *dwContext* по умолчанию для задания идентификатора контекста в значение по своему выбору. Идентификатор контекста связан с этой конкретной операции из `CFtpConnection` объект, созданный с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение для [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="putfile"></a>  CFtpConnection::PutFile

Вызовите эту функцию-член для хранения файла на FTP-сервера.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pstrLocalFile*<br/>
Указатель на строку, содержащую имя файла для отправки из локальной системы.

*pstrRemoteFile*<br/>
Указатель на строку, содержащую имя файла, создаваемого на FTP-сервере.

*dwFlags*<br/>
Определяет условия, при которых происходит передача файла. Может быть любой из констант FTP_TRANSFER_ *, описанных в [OpenFile](#openfile).

*dwContext*<br/>
Идентификатор контекста для размещения файла. См. в разделе **"Примечания"** Дополнительные сведения о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

`PutFile` — Это высокоуровневый подпрограмму, которая обрабатывает все операции, связанные с хранением файла на FTP-сервера. Приложения, которые только отправляют данные или требуют более тщательно контролировать передачу файла, должны использовать [OpenFile](#openfile) и [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).

Переопределить `dwContext` по умолчанию для задания идентификатора контекста в значение по своему выбору. Идентификатор контекста связан с этой конкретной операции из `CFtpConnection` объект, созданный с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение для [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с которой он определен. См. в статье [Internet первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.

##  <a name="remove"></a>  CFtpConnection::Remove

Вызовите эту функцию-член для удаления указанного файла из подключенного сервера.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Параметры

*pstrFileName*<br/>
Указатель на строку, содержащую имя файла для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

*PstrFileName* параметр может быть либо частично определенное имя файла в текущий каталог относительный или полный путь. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `Remove` Функция преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory

Вызовите эту функцию-член для удаления указанного каталога из подключенного сервера.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель на строку, содержащую каталог для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте [GetCurrentDirectory](#getcurrentdirectory) чтобы определить текущий рабочий каталог на сервере. Не следует предполагать, что удаленная система подключился вы к корневому каталогу.

*PstrDirName* параметр может быть либо полное или сокращенное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `RemoveDirectory` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="rename"></a>  CFtpConnection::Rename

Вызовите эту функцию-член переименовать указанный файл на подключенном сервере.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Параметры

*pstrExisting*<br/>
Указатель на строку, содержащую имя текущего файла, который требуется переименовать.

*pstrNew*<br/>
Указатель на строку, содержащую новое имя файла.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

*PstrExisting* и *pstrNew* параметры могут быть либо частично определенное имя файла в текущий каталог относительный или полный путь. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `Rename` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

##  <a name="setcurrentdirectory"></a>  CFtpConnection::SetCurrentDirectory

Вызовите эту функцию-член можно переключиться в другой каталог на FTP-сервера.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель на строку, содержащую имя каталога.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) может вызываться для определения причины ошибки.

### <a name="remarks"></a>Примечания

*PstrDirName* параметр может быть либо полное или сокращенное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `SetCurrentDirectory` Преобразует разделителей имя каталога, в соответствующие символы, прежде чем они используются.

Используйте [GetCurrentDirectory](#getcurrentdirectory) для определения текущего рабочего каталога FTP-сервера. Не следует предполагать, что удаленная система подключился вы к корневому каталогу.

## <a name="see-also"></a>См. также

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
