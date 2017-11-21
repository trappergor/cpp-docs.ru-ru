---
title: "Класс классе CFtpConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a800ff5c8c071e966bbc1e5297fb706627c8d17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cftpconnection-class"></a>Класс классе CFtpConnection
Управляет FTP-подключением к Интернет-серверу и позволяет напрямую управлять каталогов и файлов на этом сервере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|Создает объект `CFtpConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|Отправляет команду напрямую на FTP-сервер.|  
|[CFtpConnection::CreateDirectory](#createdirectory)|Создает каталог на сервере.|  
|[CFtpConnection::GetCurrentDirectory](#getcurrentdirectory)|Возвращает текущий каталог для этого подключения.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Возвращает текущий каталог для этого подключения, URL-адрес.|  
|[CFtpConnection::GetFile](#getfile)|Получает файл из подключенного сервера|  
|[CFtpConnection::OpenFile](#openfile)|Открывает файл на подключенном сервере.|  
|[CFtpConnection::PutFile](#putfile)|Помещает файл на сервере.|  
|[CFtpConnection::Remove](#remove)|Удаляет файл на сервере.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Удаляет указанный каталог на сервере.|  
|[CFtpConnection::Rename](#rename)|Переименовывает файл на сервере.|  
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Задает текущий каталог FTP.|  
  
## <a name="remarks"></a>Примечания  
 FTP является одним из трех служб Интернета, распознаваемые классов MFC WinInet.  
  
 Для связи с FTP веб-сервером, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создать `CFtpConnection` объекта. Никогда не создавайте `CFtpConnection` объекта напрямую; вместо этого вызовите [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), которая создает `CFtpConnection` объекта и возвращает указатель на него.  
  
 Дополнительные сведения о том, как `CFtpConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о взаимодействии с другими поддерживается двумя службы, HTTP и gopher, просмотреть классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Пример  
  См. пример в [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Общие сведения о классе.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cftpconnection"></a>CFtpConnection::CFtpConnection  
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
 `pSession`  
 Указатель на связанный [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.  
  
 `hConnected`  
 Дескриптор Windows текущего сеанса Интернета.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя FTP-сервера.  
  
 `dwContext`  
 Идентификатор контекста для операции. `dwContext`Определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию имеет значение 1; Тем не менее можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связана с этим идентификатором контекста.  
  
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
  
 `nPort`  
 Число, определяющее порт TCP/IP, используемый на сервере.  
  
 `bPassive`  
 Задает пассивный или активный режим для этого сеанса FTP. Если значение **TRUE**, он задает Win32 API `dwFlag` для **INTERNET_FLAG_PASSIVE**.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CFtpConnection` объекта напрямую. Вместо этого необходимо вызвать [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), которая создает **CFptConnection** объекта.  
  
##  <a name="command"></a>CFtpConnection::Command  
 Отправляет команду напрямую на FTP-сервер.  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pszCommand`  
 Указатель на строку, содержащую отправляемую команду.  
  
 *eResponse*  
 Определяет, следует ли ожидать ответ FTP-сервера. Может принимать одно из следующих значений:  
  
- **CmdRespNone** — ответ не ожидается.  
  
- **CmdRespRead** — ответ ожидается.  
  
 `dwFlags`  
 Значение, содержащее флаги, управляющие этой функцией. Полный список см. в разделе [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 `dwContext`  
 Указатель на значение, содержащее определяемое приложением значение, используемое для идентификации контекста приложения в обратных вызовах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) функции, как описано в Windows SDK.  
  
 В случае ошибки MFC вызывает исключение типа [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="createdirectory"></a>CFtpConnection::CreateDirectory  
 Вызовите эту функцию-член для создания каталога на подключенном сервере.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую имя каталога для создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Windows [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `GetCurrentDirectory` определить текущий рабочий каталог для этого подключения к серверу. Не следует предполагать, что удаленной системе подключен вы в корневой каталог.  
  
 `pstrDirName` Параметр может быть либо частично или полностью уточненное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `CreateDirectory`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="getcurrentdirectory"></a>CFtpConnection::GetCurrentDirectory  
 Вызовите эту функцию-член для получения имени текущего каталога.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strDirName`  
 Ссылка на строку, которая получит имя каталога.  
  
 `pstrDirName`  
 Указатель на строку, которая получит имя каталога.  
  
 `lpdwLen`  
 Указатель на значение DWORD, содержащее следующие сведения:  
  
|||  
|-|-|  
|При входе|Размер буфера, на который указывает `pstrDirName`.|  
|При возврате|Число символов, сохраненных в `pstrDirName`. Если функция-член, происходит сбой и возвращается значение ERROR_INSUFFICIENT_BUFFER, затем `lpdwLen` содержит число байтов, которые приложение должно выделить для получения строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить имя каталога URL-адрес, вызовите [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Параметры `pstrDirName` или `strDirName` может быть либо частичные имена файлов относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetCurrentDirectory`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL  
 Вызовите эту функцию-член для получения имени текущего каталога, как URL-адрес.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strDirName`  
 Ссылка на строку, которая получит имя каталога.  
  
 `pstrDirName`  
 Указатель на строку, которая получит имя каталога.  
  
 `lpdwLen`  
 Указатель на значение DWORD, содержащее следующие сведения:  
  
|||  
|-|-|  
|При входе|Размер буфера, на который указывает `pstrDirName`.|  
|При возврате|Число символов, сохраненных в `pstrDirName`. Если функция-член, происходит сбой и возвращается значение ERROR_INSUFFICIENT_BUFFER, затем `lpdwLen` содержит число байтов, которые приложение должно выделить для получения строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `GetCurrentDirectoryAsURL`работает так же, как [GetCurrentDirectory](#getcurrentdirectory)  
  
 Параметр `strDirName` может быть либо частичные имена файлов относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetCurrentDirectoryAsURL`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="getfile"></a>CFtpConnection::GetFile  
 Вызовите эту функцию-член для получения файла с FTP-сервера и их сохранения на локальном компьютере.  
  
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
 `pstrRemoteFile`  
 Указатель символом null строку, содержащую имя файла для извлечения с FTP-сервера.  
  
 `pstrLocalFile`  
 Указатель символом null строку, содержащую имя файла для создания локального компьютера.  
  
 *bFailIfExists*  
 Указывает, является ли имя файла может уже использоваться существующий файл. Если имя локального файла уже существует, и этот параметр является **TRUE**, `GetFile` завершается ошибкой. В противном случае `GetFile` удалит существующую копию файла.  
  
 `dwAttributes`  
 Указывает атрибуты файла. Это может быть любое сочетание следующих флагов FILE_ATTRIBUTE_ *.  
  
-   FILE_ATTRIBUTE_ARCHIVE файл представляет собой файл архива. Приложения используют этот атрибут, чтобы пометить файлы для резервного копирования или удаления.  
  
-   Сжимается FILE_ATTRIBUTE_COMPRESSED к файлу или каталогу. Для файла сжатия означает, что все данные в файл сжимается. Для каталога сжатие значение по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
-   FILE_ATTRIBUTE_DIRECTORY файл является каталогом.  
  
-   FILE_ATTRIBUTE_NORMAL файл имеет другие атрибуты не установлены. Этот атрибут действителен только в том случае, если используется отдельно. Все остальные атрибуты файла переопределить FILE_ATTRIBUTE_NORMAL:  
  
-   FILE_ATTRIBUTE_HIDDEN файл будет скрыта. Это не должно включаться в обычный список каталога.  
  
-   FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но нельзя записать в него или удалите его.  
  
-   FILE_ATTRIBUTE_SYSTEM файл является частью или используется исключительно операционной системой.  
  
-   FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Запись в файл приложения следует только в том случае, если это действительно необходимо. Большая часть файла данных остается в памяти без, записываемых на носитель, так как файл будут удалены.  
  
 `dwFlags`  
 Определяет условия, при которых происходит передача. Этот параметр может иметь любой из `dwFlags` значений описано в [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) в Windows SDK.  
  
 `dwContext`  
 Идентификатор контекста для получения файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `GetFile`Это высокоуровневое подпрограмму, которая обрабатывает все дополнительные расходы, связанные с чтением файла с FTP-сервера и сохранить их локально. Приложения, только для извлечения файлов данных или требуют закрыть контроль над передачи файла, должны использовать `OpenFile` и [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) вместо него.  
  
 Если `dwFlags` FILE_TRANSFER_TYPE_ASCII преобразования из файла данных также преобразует управления и форматирование символов для эквивалентов Windows. Передача по умолчанию является двоичном режиме, где файл загружается в тот же формат, хранящегося на сервере.  
  
 Оба `pstrRemoteFile` и `pstrLocalFile` может быть либо частичные имена файлов относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `GetFile`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
 Переопределить `dwContext` по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста связан с этой определенной операции `CFtpConnection` объектом, созданным с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="openfile"></a>CFtpConnection::OpenFile  
 Вызовите эту функцию-член для открытия файла на FTP-сервера для чтения или записи.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrFileName`  
 Указатель на строку, содержащую имя файла для открытия.  
  
 *dwAccess*  
 Определяет способ доступа к файлу. Может быть GENERIC_READ или GENERIC_WRITE, но не оба.  
  
 `dwFlags`  
 Определяет условия, при которых последующих перенос. Это может иметь любое из следующих констант FTP_TRANSFER_ *.  
  
-   FTP_TRANSFER_TYPE_ASCII файл передается с помощью метода передачи FTP ASCII (типа А). Преобразует элемент управления и сведения о форматировании в локальные эквиваленты.  
  
-   FTP_TRANSFER_TYPE_BINARY файл передает данные с помощью метода передачи образа FTP's (тип I). Существует передачу файлов данных точно в том виде, без изменений. Это метод передачи по умолчанию.  
  
 `dwContext`  
 Идентификатор контекста для открытия файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [классе CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `OpenFile`следует использовать в следующих ситуациях:  
  
-   Приложение имеет данные, которые должны быть отправлены и создан в виде файла с FTP-сервера, но, что данные не в локальном файле. Один раз `OpenFile` открывает файл, используемых приложением [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) для отправки данных в файле FTP на сервер.  
  
-   Приложение должно получить файл с сервера и поместите его в память, управляемые приложения, вместо записи на диск. Приложение использует [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) после использования `OpenFile` для открытия файла.  
  
-   Приложению требуется высокий уровень контроля над передачи файла. Например, приложение может потребоваться отобразить ход выполнения управления отображения хода состояние передачи файлов при загрузке файла.  
  
 После вызова метода `OpenFile` и до вызова метода **CInternetConnection::Close**, приложение может вызывать только [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), **CInternetConnection::Close**, или [CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Для вызовов других функций FTP на один сеанс FTP не удастся и задать код ошибки для FTP_ETRANSFER_IN_PROGRESS.  
  
 `pstrFileName` Параметр может быть именем частичные файла, относительным для текущего каталога или полным путем. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `OpenFile`Преобразует разделителей имя каталога в соответствующие символы перед его использованием.  
  
 Переопределить `dwContext` по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста связан с этой определенной операции `CFtpConnection` объектом, созданным с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="putfile"></a>CFtpConnection::PutFile  
 Вызовите эту функцию-член для сохранения файла на FTP-сервере.  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrLocalFile`  
 Указатель на строку, содержащую имя файла для отправки из локальной системы.  
  
 `pstrRemoteFile`  
 Указатель на строку, содержащую имя файла для создания на FTP-сервере.  
  
 `dwFlags`  
 Определяет условия, при которых происходит передача файла. Может иметь любое из констант FTP_TRANSFER_ *, описанных в [OpenFile](#openfile).  
  
 `dwContext`  
 Идентификатор контекста для размещения файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `PutFile`Это высокоуровневое подпрограмму, которая отвечает за выполнение всех операций, связанных с хранением файлов с FTP-сервера. Приложения, которые только отправляют данные или требуют более тщательно контролировать передачу файла, должны использовать [OpenFile](#openfile) и [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Переопределить `dwContext` по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста связан с этой определенной операции `CFtpConnection` объектом, созданным с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="remove"></a>CFtpConnection::Remove  
 Вызовите эту функцию-член для удаления указанного файла из подключенного сервера.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrFileName`  
 Указатель на строку, содержащую имя файла для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrFileName` Параметр может быть именем частичные файла, относительным для текущего каталога или полным путем. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. **Удалить** функция преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="removedirectory"></a>CFtpConnection::RemoveDirectory  
 Вызовите эту функцию-член для удаления указанного каталога из подключенного сервера.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую каталога должны быть удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте [GetCurrentDirectory](#getcurrentdirectory) определить текущий рабочий каталог на сервере. Не следует предполагать, что удаленной системе подключен вы в корневой каталог.  
  
 `pstrDirName` Параметр может быть либо частично или полностью уточненное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `RemoveDirectory`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="rename"></a>CFtpConnection::Rename  
 Вызовите эту функцию-член можно переименовать файл, указанный на подключенном сервере.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrExisting`  
 Указатель на строку, содержащую имя текущего файла, который требуется переименовать.  
  
 `pstrNew`  
 Указатель на строку, содержащую имя нового файла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrExisting` И `pstrNew` параметров может быть именем частичные файла, относительным для текущего каталога или полным путем. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. **Переименование** преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
##  <a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory  
 Вызовите эту функцию-член для изменения в другой каталог на FTP-сервере.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую имя каталога.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrDirName` Параметр может быть либо частично или полностью уточненное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/) можно использовать в качестве разделителя каталогов для либо имя. `SetCurrentDirectory`Преобразует разделителей имя каталога в соответствующие символы перед их использованием.  
  
 Используйте [GetCurrentDirectory](#getcurrentdirectory) определить текущий рабочий каталог на FTP-сервер. Не следует предполагать, что удаленной системе подключен вы в корневой каталог.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
