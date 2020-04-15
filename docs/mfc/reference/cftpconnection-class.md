---
title: Класс CFtpConnection
ms.date: 08/29/2019
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
ms.openlocfilehash: a1fe516869aa98cc291597211eee175ef591e45d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373779"
---
# <a name="cftpconnection-class"></a>Класс CFtpConnection

Управляет подключением FTP к интернет-серверу и позволяет прямо манипулировать каталогами и файлами на этом сервере.

## <a name="syntax"></a>Синтаксис

```
class CFtpConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFtpConnection::CFtpConnection](#cftpconnection)|Формирует объект `CFtpConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFtpConnection::Command](#command)|Отправляет команду напрямую на FTP-сервер.|
|[CFtpConnection::CreateDirectory](#createdirectory)|Создает каталог на сервере.|
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Получает текущий каталог для этого соединения.|
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Получает текущий каталог для этого соединения в качестве URL-адреса.|
|[CFtpConnection::GetFile](#getfile)|Получает файл с подключенного сервера|
|[CFtpConnection::OpenFile](#openfile)|Открывает файл на подключенном сервере.|
|[CFtpConnection::PutFile](#putfile)|Размещает файл на сервере.|
|[CFtpConnection::Удалить](#remove)|Удаляет файл с сервера.|
|[CFtpConnection::RemoveDirectory](#removedirectory)|Удаляет указанный каталог с сервера.|
|[CFtpConnection::Переименование](#rename)|Переименуем файл на сервере.|
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Устанавливает текущий каталог FTP.|

## <a name="remarks"></a>Remarks

FTP является одним из трех интернет-сервисов, признанных классами MFC WinInet.

Чтобы общаться с интернет-сервером FTP, необходимо сначала создать экземпляр `CFtpConnection` [CInternetSession,](../../mfc/reference/cinternetsession-class.md)а затем создать объект. Вы никогда `CFtpConnection` не создаете объект напрямую; скорее, позвоните [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает `CFtpConnection` объект и возвращает указатель к нему.

Чтобы узнать `CFtpConnection` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md) Для получения дополнительной информации об общении с двумя другими поддерживаемыми [CGopherConnection](../../mfc/reference/cgopherconnection-class.md)службами, HTTP и сусликами, [см.](../../mfc/reference/chttpconnection-class.md)

## <a name="example"></a>Пример

  Смотрите пример в обзоре класса [CFtpFileFind.](../../mfc/reference/cftpfilefind-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CFtpConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>CFtpConnection::CFtpConnection

Эта функция члена называется `CFtpConnection` для построения объекта.

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

*pСессия*<br/>
Указатель на связанный объект [CInternetSession.](../../mfc/reference/cinternetsession-class.md)

*hПодключено*<br/>
Ручка Windows текущей сессии Интернета.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера FTP.

*Dwcontext*<br/>
Идентификатор контекста для операции. *dwContext* определяет информацию о состоянии операции, возвращенную [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию устанавливается на 1; однако можно явно назначить идентификатор контекста для операции. Объект и любая работа, которую он выполняет, будут связаны с идентификатором контекста.

*pstrUserName*<br/>
Указатель на строку с нулевым завершением, которая определяет имя пользователя для входа в систему. Если NULL, по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на строку с нулевым завершением, которая определяет пароль для входа в систему. Если *pstrPassword* и *pstrUserName* являются NULL, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *pstrPassword* является NULL (или пустой строки), но *pstrUserName* не является NULL, пустой пароль используется. В следующей таблице описывается поведение для четырех возможных настроек *pstrUserName* и *pstrPassword:*

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправленное на сервер FTP|Пароль, отправленный на сервер FTP|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL или "|NULL или "|"анонимный"|Имя пользователя по электронной почте|
|Не-NULL строка|NULL или "|*pstrUserName*|" "|
|NULL Non- NULL String|ошибка|ошибка||
|Не-NULL строка|Не-NULL строка|*pstrUserName*|*pstrPassword*|

*nПорт*<br/>
Номер, идентифицирующие порт TCP/IP для использования на сервере.

*bPassive*<br/>
Определяет пассивный или активный режим для этой сессии FTP. Если установить на истину, он устанавливает Win32 API *dwFlag* INTERNET_FLAG_PASSIVE.

### <a name="remarks"></a>Remarks

Вы никогда `CFtpConnection` не создаете объект напрямую. Вместо этого позвоните `CFptConnection` [cInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает объект.

## <a name="cftpconnectioncommand"></a><a name="command"></a>CFtpConnection::Command

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
Уточняется, ожидается ли ответ от сервера FTP. Может использоваться одно из следующих значений:

- `CmdRespNone`Ответа не ожидается.
- `CmdRespRead`Ожидается ответ.
- `CmdRespWrite`Не используется.

CmdResponseType является членом CFtpConnection, определяется в *afxinet.h*.

*dwFlags*<br/>
Значение, содержащее флаги, управляющие этой функцией. Полный список [можно](/windows/win32/api/wininet/nf-wininet-ftpcommandw)оперетизнять.

*Dwcontext*<br/>
Указатель на значение, содержащее определяемое приложением значение, используемое для идентификации контекста приложения в обратных вызовах.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Remarks

Эта функция члена эмулирует функциональность функции [FTPCommand,](/windows/win32/api/wininet/nf-wininet-ftpcommandw) как описано в SDK Windows.

Если ошибка происходит, MFC бросает исключение типа [CInternetException](../../mfc/reference/cinternetexception-class.md).

## <a name="cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>CFtpConnection::CreateDirectory

Вызовите эту функцию участника для создания каталога на подключенном сервере.

```
BOOL CreateDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель строки, содержащей имя каталога для создания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Windows [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Используйте `GetCurrentDirectory` для определения текущего рабочего каталога для этого подключения к серверу. Не думайте, что удаленная система подключила вас к корневому каталогу.

Параметр `pstrDirName` может быть либо частично, либо полностью квалифицированным файловым именем относительно текущего каталога. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `CreateDirectory`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

## <a name="cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>CFtpConnection::GetCurrentDirectory

Вызовите эту функцию участника, чтобы получить имя текущего каталога.

```
BOOL GetCurrentDirectory(CString& strDirName) const;

BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Параметры

*strDirName*<br/>
Ссылка на строку, которая получит название каталога.

*pstrDirName*<br/>
Указатель на строку, которая получит название каталога.

*lpdwLen*<br/>
Указатель на DWORD, содержащий следующую информацию:

|||
|-|-|
|На входе|Размер буфера, на который ссылается *pstrDirName*.|
|По возвращении|Количество символов, хранящихся в *pstrDirName*. Если функция члена выходит из строя и ERROR_INSUFFICIENT_BUFFER возвращается, то *lpdwLen* содержит количество байтов, которые приложение должно выделить для получения строки.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Чтобы получить имя каталога в качестве URL вместо этого, позвоните [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).

Параметры *pstrDirName* или *strDirName* могут быть либо частично квалифицированными именами файлов по отношению к текущему каталогу, либо полностью квалифицированными. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `GetCurrentDirectory`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

## <a name="cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL

Вызовите эту функцию участника, чтобы получить имя текущего каталога в качестве URL-адреса.

```
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;

BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,
    LPDWORD lpdwLen) const;
```

### <a name="parameters"></a>Параметры

*strDirName*<br/>
Ссылка на строку, которая получит название каталога.

*pstrDirName*<br/>
Указатель на строку, которая получит название каталога.

*lpdwLen*<br/>
Указатель на DWORD, содержащий следующую информацию:

|||
|-|-|
|На входе|Размер буфера, на который ссылается *pstrDirName*.|
|По возвращении|Количество символов, хранящихся в *pstrDirName*. Если функция члена выходит из строя и ERROR_INSUFFICIENT_BUFFER возвращается, то *lpdwLen* содержит количество байтов, которые приложение должно выделить для получения строки.|

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

`GetCurrentDirectoryAsURL`ведет себя так же, как [GetCurrentDirectory](#getcurrentdirectory)

Параметр *strDirName* может быть либо частично квалифицированным файловым именем по отношению к текущему каталогу, либо полностью квалифицированным. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `GetCurrentDirectoryAsURL`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

## <a name="cftpconnectiongetfile"></a><a name="getfile"></a>CFtpConnection::GetFile

Вызов эту функцию участника, чтобы получить файл с сервера FTP и хранить его на локальной машине.

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
Указатель на нулевую строку, содержащую имя файла для извлечения с сервера FTP.

*pstrLocalFile*<br/>
Указатель на нулевую строку, содержащую имя файла для создания в локальной системе.

*bFailIfExists*<br/>
Указывает, может ли имя файла уже использоваться существующим файлом. Если локальное имя файла уже существует, `GetFile` и этот параметр является правдой, сбой. В `GetFile` противном случае стереть существующую копию файла.

*dwАтрибуты*<br/>
Указывает атрибуты файла. Это может быть любое сочетание следующих FILE_ATTRIBUTE_ флагов.

- FILE_ATTRIBUTE_ARCHIVE Файл является архивным файлом. Приложения используют этот атрибут для обозначения файлов для резервного копирования или удаления.

- FILE_ATTRIBUTE_COMPRESSED файл или каталог сжимается. Для файла сжатие означает, что все данные в файле сжаты. Для каталога сжатие — это значение по умолчанию для вновь созданных файлов и субдиректоров.

- FILE_ATTRIBUTE_DIRECTORY Файл является каталогом.

- FILE_ATTRIBUTE_NORMAL файл не имеет других наборов атрибутов. Этот атрибут действителен только при использовании в одиночку. Все остальные атрибуты файла переопределяют FILE_ATTRIBUTE_NORMAL:

- FILE_ATTRIBUTE_HIDDEN Файл скрыт. Он не должен быть включен в обычный список каталогов.

- FILE_ATTRIBUTE_READONLY Файл читается только. Приложения могут читать файл, но не могут написать на него или удалить его.

- FILE_ATTRIBUTE_SYSTEM Файл является частью или используется исключительно операционной системой.

- FILE_ATTRIBUTE_TEMPORARY Файл используется для временного хранения. Заявки должны писать в файл только в случае крайней необходимости. Большая часть данных файла остается в памяти, не будучи смыты к средствам массовой информации, потому что файл скоро будет удален.

*dwFlags*<br/>
Определяет условия, при которых происходит передача. Этот параметр может быть любым из значений *dwFlags,* описанных в [FtpGetFile](/windows/win32/api/wininet/nf-wininet-ftpgetfilew) в Windows SDK.

*Dwcontext*<br/>
Идентификатор контекста для поиска файла. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

`GetFile`— это рутина высокого уровня, которая обрабатывает все накладные расходы, связанные с чтением файла с сервера FTP и хранением его локально. Приложения, которые только получить данные файла, или которые `OpenFile` требуют тщательного контроля над передачей файла, должны использовать и [CInternetFile::Читать](../../mfc/reference/cinternetfile-class.md#read) вместо.

Если *dwFlags* FILE_TRANSFER_TYPE_ASCII, перевод файловых данных также преобразует элементы управления и форматирования в эквиваленты Windows. Передача по умолчанию — это двоичный режим, в котором файл загружается в том же формате, что и хранится на сервере.

Как *pstrRemoteFile,* так и *pstrLocalFile* могут быть либо частично квалифицированными именами файлов по отношению к текущему каталогу, либо полностью квалифицированными. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `GetFile`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

Переизбь по умолчанию *dwContext,* чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста связан с `CFtpConnection` этой конкретной операцией объекта, созданного его объектом [CInternetSession.](../../mfc/reference/cinternetsession-class.md) Значение возвращается [в CInternetSession::OnStatusCallback,](../../mfc/reference/cinternetsession-class.md#onstatuscallback) чтобы предоставить статус операции, с которой он идентифицирован. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="cftpconnectionopenfile"></a><a name="openfile"></a>CFtpConnection::OpenFile

Вызовите эту функцию участника, чтобы открыть файл, расположенный на сервере FTP для чтения или записи.

```
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,
    DWORD dwAccess = GENERIC_READ,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pstrFileName*<br/>
Указатель строки, содержащей имя открываемого файла.

*dwAccess*<br/>
Определяет, как будет доступен файл. Может быть как GENERIC_READ, так и GENERIC_WRITE, но не оба.

*dwFlags*<br/>
Определяет условия, при которых происходят последующие переводы. Это может быть любой из следующих констант FTP_TRANSFER_»:

- FTP_TRANSFER_TYPE_ASCII Файл передается с помощью метода передачи FTP ASCII (тип A). Преобразует контроль и форматирование информации в локальные эквиваленты.

- FTP_TRANSFER_TYPE_BINARY Файл передает данные с помощью метода передачи изображения FTP (тип I). Файл передает данные точно так, как он существует, без каких-либо изменений. Это метод передачи по умолчанию.

*Dwcontext*<br/>
Идентификатор контекста для открытия файла. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CInternetFile.](../../mfc/reference/cinternetfile-class.md)

### <a name="remarks"></a>Remarks

`OpenFile`должны использоваться в следующих ситуациях:

- Приложение имеет данные, которые должны быть отправлены и созданы в виде файла на сервере FTP, но эти данные не в локальном файле. После `OpenFile` открытия файла приложение использует [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) для отправки данных файла FTP на сервер.

- Приложение должно получить файл с сервера и поместить его в контролируемую приложением память, вместо того, чтобы записывать его на диск. Приложение использует [CInternetFile::Прочитайте](../../mfc/reference/cinternetfile-class.md#read) после использования, `OpenFile` чтобы открыть файл.

- Приложение нуждается в тонком уровне контроля над передачей файлов. Например, приложение может захотеть отобразить элемент управления ходом выполнения, указывающий на ход работы статуса передачи файла при загрузке файла.

После `OpenFile` вызова и `CInternetConnection::Close`до вызова, приложение может звонить только [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:::Запись](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`или [CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Вызовы на другие функции FTP для того же сеанса FTP сбой и установить код ошибки, чтобы FTP_ETRANSFER_IN_PROGRESS.

Параметр *pstrFileName* может быть либо частично квалифицированным файловым наименованием по отношению к текущему каталогу, либо полностью квалифицированным. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `OpenFile`перед его использованием сепараторы имен каталога переводят их на соответствующие символы.

Переизбь по умолчанию *dwContext,* чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста связан с `CFtpConnection` этой конкретной операцией объекта, созданного его объектом [CInternetSession.](../../mfc/reference/cinternetsession-class.md) Значение возвращается [в CInternetSession::OnStatusCallback,](../../mfc/reference/cinternetsession-class.md#onstatuscallback) чтобы предоставить статус операции, с которой он идентифицирован. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="cftpconnectionputfile"></a><a name="putfile"></a>CFtpConnection::PutFile

Вызовите эту функцию участника для хранения файла на сервере FTP.

```
BOOL PutFile(
    LPCTSTR pstrLocalFile,
    LPCTSTR pstrRemoteFile,
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pstrLocalFile*<br/>
Указатель строки, содержащей имя файла для отправки из локальной системы.

*pstrRemoteFile*<br/>
Указатель строки, содержащей имя файла для создания на сервере FTP.

*dwFlags*<br/>
Определяет условия, при которых происходит передача файла. Может быть любой из констант FTP_TRANSFER_, описанных в [OpenFile](#openfile).

*Dwcontext*<br/>
Идентификатор контекста для размещения файла. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

`PutFile`— это рутина высокого уровня, которая обрабатывает все операции, связанные с хранением файла на сервере FTP. Приложения, которые отправляют только данные или требуют более тщательного контроля над передачей файлов, должны использовать [OpenFile](#openfile) и [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).

Переувитрите `dwContext` значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста связан с `CFtpConnection` этой конкретной операцией объекта, созданного его объектом [CInternetSession.](../../mfc/reference/cinternetsession-class.md) Значение возвращается [в CInternetSession::OnStatusCallback,](../../mfc/reference/cinternetsession-class.md#onstatuscallback) чтобы предоставить статус операции, с которой он идентифицирован. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="cftpconnectionremove"></a><a name="remove"></a>CFtpConnection::Удалить

Вызов эту функцию участника, чтобы удалить указанный файл с подключенного сервера.

```
BOOL Remove(LPCTSTR pstrFileName);
```

### <a name="parameters"></a>Параметры

*pstrFileName*<br/>
Указатель на строку, содержащую имя файла для удаления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Параметр *pstrFileName* может быть либо частично квалифицированным файловым наименованием по отношению к текущему каталогу, либо полностью квалифицированным. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. Функция `Remove` переводит сепараторы имен каталога в соответствующие символы, прежде чем они будут использованы.

## <a name="cftpconnectionremovedirectory"></a><a name="removedirectory"></a>CFtpConnection::RemoveDirectory

Вызов эту функцию участника, чтобы удалить указанный каталог с подключенного сервера.

```
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель на строку, содержащую каталог, который будет удален.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Используйте [GetCurrentDirectory](#getcurrentdirectory) для определения текущего рабочего каталога сервера. Не думайте, что удаленная система подключила вас к корневому каталогу.

Параметр *pstrDirName* может быть либо частично, либо полностью квалифицированным файловым именем по отношению к текущему каталогу. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `RemoveDirectory`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

## <a name="cftpconnectionrename"></a><a name="rename"></a>CFtpConnection::Переименование

Вызовите эту функцию участника, чтобы переименовать указанный файл на подключенном сервере.

```
BOOL Rename(
    LPCTSTR pstrExisting,
    LPCTSTR pstrNew);
```

### <a name="parameters"></a>Параметры

*pstrExisting*<br/>
Указатель строки, содержащей текущее имя файла для переименования.

*pstrNew*<br/>
Указатель строки, содержащей новое имя файла.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Параметры *pstrExisting* и *pstrNew* могут быть либо частично квалифицированным файловым именем относительно текущего каталога, либо полностью квалифицированными. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `Rename`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

## <a name="cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory

Вызовите эту функцию участника, чтобы изменить на другой каталог на сервере FTP.

```
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```

### <a name="parameters"></a>Параметры

*pstrDirName*<br/>
Указатель на строку, содержащую название каталога.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Remarks

Параметр *pstrDirName* может быть либо частично, либо полностью квалифицированным файловым именем по отношению к текущему каталогу. Backslash (\\) или вперед слэш (/) может быть использован в качестве каталога сепаратора для любого имени. `SetCurrentDirectory`переводит сепараторы имен каталога в соответствующие символы перед их использователем.

Используйте [GetCurrentDirectory](#getcurrentdirectory) для определения текущего рабочего каталога сервера FTP. Не думайте, что удаленная система подключила вас к корневому каталогу.

## <a name="see-also"></a>См. также раздел

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
