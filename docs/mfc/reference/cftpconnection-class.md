---
title: "Класс CFtpConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection class
- FTP (File Transfer Protocol), establishing connections
- Internet connections, FTP
- Internet services, FTP
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ebfe4078bf70d0afc2d36a222b61c11dbaf7c64d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cftpconnection-class"></a>Класс CFtpConnection
Управление подключением к Интернет-серверу FTP и позволяет напрямую управлять каталогов и файлов на этом сервере.  
  
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
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Возвращает текущий каталог для этого подключения, URL-адреса.|  
|[CFtpConnection::GetFile](#getfile)|Получает файл из подключенного сервера|  
|[CFtpConnection::OpenFile](#openfile)|Открытие файла на подключенном сервере.|  
|[CFtpConnection::PutFile](#putfile)|Помещает файл на сервере.|  
|[CFtpConnection::Remove](#remove)|Удаляет файл с сервера.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Удаляет указанный каталог на сервере.|  
|[CFtpConnection::Rename](#rename)|Переименование файла на сервере.|  
|[CFtpConnection::SetCurrentDirectory](#setcurrentdirectory)|Задает текущий каталог FTP.|  
  
## <a name="remarks"></a>Примечания  
 FTP — один из трех служб Интернета, распознаваемые классов MFC WinInet.  
  
 Взаимодействие с сервером в Интернете FTP, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем создать `CFtpConnection` объекта. Никогда не создавать `CFtpConnection` напрямую; вместо этого вызвать метод [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает `CFtpConnection` объекта и возвращает указатель на него.  
  
 Дополнительные сведения о том, как `CFtpConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения о взаимодействии с двух других поддерживаемых служб HTTP и gopher, просмотреть классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Пример  
  Пример см. в [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Общие сведения о классе.  
  
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
 Указатель на связанную [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.  
  
 `hConnected`  
 Дескриптор Windows текущего сеанса Интернета.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя FTP-сервера.  
  
 `dwContext`  
 Идентификатор контекста для операции. `dwContext`Определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). По умолчанию используется значение 1; Однако можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связан с этим идентификатором контекста.  
  
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
  
 `nPort`  
 Число, идентифицирующее порт TCP/IP, используемый на сервере.  
  
 `bPassive`  
 Задает пассивный или активный режим для этого сеанса FTP. Если значение **TRUE**, он задает Win32 API `dwFlag` для **INTERNET_FLAG_PASSIVE**.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CFtpConnection` напрямую. Вместо этого необходимо вызвать [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), который создает **CFptConnection** объекта.  
  
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
  
- **CmdRespNone** отклики не ожидаются.  
  
- **CmdRespRead** ожидается ответ.  
  
 `dwFlags`  
 Значение, содержащее флаги, управляющие этой функцией. Полный список см. в разделе [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 `dwContext`  
 Указатель на значение, содержащее определяемое приложением значение, используемое для идентификации контекста приложения в обратных вызовах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член эмулирует работу [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) функции, как описано в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Если возникает ошибка, MFC создает исключение типа [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="createdirectory"></a>CFtpConnection::CreateDirectory  
 Вызовите эту функцию-член для создания каталога на подключенном сервере.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую имя каталога для создания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Windows [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте `GetCurrentDirectory` определить текущий рабочий каталог для этого подключения к серверу. Не следует предполагать, что удаленная система подключена вы в корневой каталог.  
  
 `pstrDirName` Параметр может быть либо частично или полное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `CreateDirectory`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
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
 Ссылка на строку, которая будет принимать имя каталога.  
  
 `pstrDirName`  
 Указатель на строку, которая будет принимать имя каталога.  
  
 `lpdwLen`  
 Указатель на значение DWORD, содержащее следующие сведения:  
  
|||  
|-|-|  
|При входе|Размер буфера, на который указывает `pstrDirName`.|  
|При возврате|Число символов, сохраненных в `pstrDirName`. Если функция-член, происходит сбой и возвращается ERROR_INSUFFICIENT_BUFFER, то `lpdwLen` содержит число байтов, которые приложение должно выделить для получения строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Чтобы получить имя каталога URL-адреса, вызовите [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Параметры `pstrDirName` или `strDirName` может быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `GetCurrentDirectory`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
##  <a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL  
 Вызовите эту функцию-член для получения имени текущего каталога URL-адреса.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `strDirName`  
 Ссылка на строку, которая будет принимать имя каталога.  
  
 `pstrDirName`  
 Указатель на строку, которая будет принимать имя каталога.  
  
 `lpdwLen`  
 Указатель на значение DWORD, содержащее следующие сведения:  
  
|||  
|-|-|  
|При входе|Размер буфера, на который указывает `pstrDirName`.|  
|При возврате|Число символов, сохраненных в `pstrDirName`. Если функция-член, происходит сбой и возвращается ERROR_INSUFFICIENT_BUFFER, то `lpdwLen` содержит число байтов, которые приложение должно выделить для получения строки.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `GetCurrentDirectoryAsURL`ведет себя так же, как [GetCurrentDirectory](#getcurrentdirectory)  
  
 Параметр `strDirName` может быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `GetCurrentDirectoryAsURL`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
##  <a name="getfile"></a>CFtpConnection::GetFile  
 Вызовите эту функцию-член для получения файла с FTP-сервера и сохранить его на локальном компьютере.  
  
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
 Указатель нулем строка, содержащая имя файла, извлекаемых из FTP-сервера.  
  
 `pstrLocalFile`  
 Указатель нулем строка, содержащая имя файла, создаваемого в локальной системе.  
  
 *bFailIfExists*  
 Указывает, является ли имя файла уже может использоваться существующий файл. Если имя локального файла уже существует, и этот параметр является **TRUE**, `GetFile` завершается ошибкой. В противном случае — `GetFile` удалит существующую копию файла.  
  
 `dwAttributes`  
 Указывает, что атрибуты файла. Это может быть любое сочетание следующих флагов FILE_ATTRIBUTE_ *.  
  
-   Файл FILE_ATTRIBUTE_ARCHIVE представляет собой файл архива. Приложения используют этот атрибут, чтобы пометить файлы для резервного копирования или удаления.  
  
-   FILE_ATTRIBUTE_COMPRESSED файл или каталог, сжимаются. Для файла сжатие означает все данные в файле сжимается. Для каталога сжатия используется по умолчанию для вновь создаваемых файлов и подкаталогов.  
  
-   FILE_ATTRIBUTE_DIRECTORY файл представляет собой каталог.  
  
-   FILE_ATTRIBUTE_NORMAL файл не имеет других атрибутов значение. Этот атрибут действителен только в том случае, если используется отдельно. Все остальные атрибуты файла переопределить FILE_ATTRIBUTE_NORMAL:  
  
-   FILE_ATTRIBUTE_HIDDEN файл является скрытым. Это не должны быть включены в обычный список каталога.  
  
-   FILE_ATTRIBUTE_READONLY файл доступен только для чтения. Приложения можно прочитать файл, но не может записать в него или удалить.  
  
-   FILE_ATTRIBUTE_SYSTEM является частью файла или используется исключительно операционной системой.  
  
-   FILE_ATTRIBUTE_TEMPORARY файл используется для временного хранения. Запись в файл приложения следует только в случае крайней необходимости. Большая часть данных файла остается в памяти без записи на диск на носитель, так как файл будут удалены.  
  
 `dwFlags`  
 Определяет условия, при которых происходит передача. Этот параметр может быть любой из `dwFlags` значения описано в [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwContext`  
 Идентификатор контекста для получения файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `GetFile`Это высокоуровневая подпрограмму, которая обрабатывает все дополнительные издержки, связанные с чтением файла с FTP-сервера и локальное хранение. Приложения, извлечь только файл данных или требуют закрыть контролировать передачу файла, следует использовать `OpenFile` и [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) вместо.  
  
 Если `dwFlags` FILE_TRANSFER_TYPE_ASCII преобразования данных файлов также преобразует управления и форматирование символы в эквиваленты в Windows. Передача по умолчанию является двоичный режим, где загрузить файл в том же формате, хранящегося на сервере.  
  
 Оба `pstrRemoteFile` и `pstrLocalFile` могут быть либо частичные имена файлов относительно текущего каталога или полное имя. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `GetFile`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
 Переопределение `dwContext` по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста связан с этой конкретной операции `CFtpConnection` объект, созданный его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния операции, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="openfile"></a>CFtpConnection::OpenFile  
 Вызовите эту функцию-член для открытия файла, расположенного на сервере FTP для чтения или записи.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrFileName`  
 Указатель на строку, содержащую имя файла, который необходимо открыть.  
  
 *dwAccess*  
 Определяет способ доступа к файлу. Может быть GENERIC_READ или GENERIC_WRITE, но не оба.  
  
 `dwFlags`  
 Указывает условия возникновения последующей передачи. Это может быть любой из следующих констант FTP_TRANSFER_ *:  
  
-   FTP_TRANSFER_TYPE_ASCII файл передается с помощью метода передачи FTP ASCII (типа А). Преобразует элемент управления и сведения о форматировании в локальные эквиваленты.  
  
-   FTP_TRANSFER_TYPE_BINARY файл для обмена данными с помощью метода передачи образа FTP's (тип I). Передача файлов данных точно так, как он существует, без изменений. Это метод передачи по умолчанию.  
  
 `dwContext`  
 Идентификатор контекста для открытия файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CInternetFile](../../mfc/reference/cinternetfile-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 `OpenFile`следует использовать в следующих ситуациях:  
  
-   Приложение имеет данные, которые должны быть отправлены и создан в виде файла на FTP-сервера, но, что данные не в локальном файле. Один раз `OpenFile` открывает файл, приложение использует [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write) для отправки файла данных FTP на сервере.  
  
-   Приложение должно получить файл с сервера и поместите его в память, управляемые приложения, вместо записи на диск. Приложение использует [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read) после использования `OpenFile` для открытия файла.  
  
-   Приложению требуется точный контроль над передачи файла. Например, приложению может потребоваться отобразить ход выполнения управления отображения хода состояние передачи файлов при загрузке файла.  
  
 После вызова метода `OpenFile` и до вызова метода **CInternetConnection::Close**, приложение может вызывать только [CInternetFile::Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write), **CInternetConnection::Close**, или [CFtpFileFind::FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Для вызовов других функций FTP для одного сеанса FTP не удастся и значение FTP_ETRANSFER_IN_PROGRESS код ошибки.  
  
 `pstrFileName` Параметр может быть либо частично определенное имя файла относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `OpenFile`Преобразует имя разделителей каталогов в соответствующие символы перед его использованием.  
  
 Переопределение `dwContext` по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста связан с этой конкретной операции `CFtpConnection` объект, созданный его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния операции, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="putfile"></a>CFtpConnection::PutFile  
 Вызовите эту функцию-член для хранения файла с FTP-сервера.  
  
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
 Указатель на строку, содержащую имя файла на FTP-сервере.  
  
 `dwFlags`  
 Определяет условия, при которых происходит передача файла. Может иметь любое из констант FTP_TRANSFER_ *, описанных в [OpenFile](#openfile).  
  
 `dwContext`  
 Идентификатор контекста для размещения файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `PutFile`Это высокоуровневая подпрограмму, которая обрабатывает все операции, связанные с хранением файлов на FTP-сервере. Приложения, отправлять данные только или требуют более тщательно контролировать передачу файла, следует использовать [OpenFile](#openfile) и [CInternetFile::Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Переопределение `dwContext` по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста связан с этой конкретной операции `CFtpConnection` объект, созданный его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния операции, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="remove"></a>CFtpConnection::Remove  
 Вызовите эту функцию-член для удаления указанного файла из подключенного сервера.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrFileName`  
 Указатель на строку, содержащую имя файла для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrFileName` Параметр может быть либо частично определенное имя файла относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. **Удаление** функция преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
##  <a name="removedirectory"></a>CFtpConnection::RemoveDirectory  
 Вызовите эту функцию-член для удаления указанного каталога из подключенного сервера.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую каталога должны быть удалены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 Используйте [GetCurrentDirectory](#getcurrentdirectory) определить текущий рабочий каталог на сервере. Не следует предполагать, что удаленная система подключена вы в корневой каталог.  
  
 `pstrDirName` Параметр может быть либо частичное или полное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `RemoveDirectory`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
##  <a name="rename"></a>CFtpConnection::Rename  
 Вызовите эту функцию-член Переименование указанного файла на подключенном сервере.  
  
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
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrExisting` И `pstrNew` параметры могут быть либо частично определенное имя файла относительно текущего каталога или полное. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. **Переименование** преобразует разделители имя каталога в соответствующие символы, прежде чем их использовать.  
  
##  <a name="setcurrentdirectory"></a>CFtpConnection::SetCurrentDirectory  
 Вызовите эту функцию-член для изменения в другой каталог на FTP-сервере.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Параметры  
 `pstrDirName`  
 Указатель на строку, содержащую имя каталога.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
### <a name="remarks"></a>Примечания  
 `pstrDirName` Параметр может быть либо частичное или полное имя файла относительно текущего каталога. Обратная косая черта (\\) или косой черты (/), которые могут использоваться в качестве разделителя каталогов для либо имя. `SetCurrentDirectory`Преобразует имя разделителей каталогов в соответствующие символы перед их использованием.  
  
 Используйте [GetCurrentDirectory](#getcurrentdirectory) определить текущий рабочий каталог на FTP-сервер. Не следует предполагать, что удаленная система подключена вы в корневой каталог.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)

