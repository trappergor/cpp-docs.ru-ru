---
title: "Класс CGopherConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- Internet server, gopher
- connecting to servers, gopher servers
- protocols, gopher
- services, gopher
- CGopherConnection class
- gopher protocol
- gopher server
- connecting to servers
- Internet connections, gopher
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6267dd226e87e5bf64faa7225e49d9a99af93e3e
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherconnection-class"></a>Класс CGopherConnection
Управление подключением к интернет-серверу gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены устарели, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Создает объект `CGopherConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Создает [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объект для поиска файлов на сервере gopher.|  
|[CGopherConnection::GetAttribute](#getattribute)|Возвращает атрибут сведения об объекте gopher.|  
|[CGopherConnection::OpenFile](#openfile)|Открывает файл gopher.|  
  
## <a name="remarks"></a>Примечания  
 Служба gopher является одним из трех служб Интернета, распознаваемые классов MFC WinInet.  
  
 Класс `CGopherConnection` содержит три дополнительных функции-члена, управление службой gopher и конструктора: [OpenFile](#openfile), [CreateLocator](#createlocator), и [GetAttribute](#getattribute).  
  
 Для взаимодействия с Интернет-серверу gopher, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md)и затем вызвать [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает `CGopherConnection` объекта и возвращает указатель на него. Никогда не создавать `CGopherConnection` напрямую.  
  
 Дополнительные сведения о том, как `CGopherConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения об использовании двух других поддерживаемых служб Интернета, FTP и HTTP в разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cgopherconnection"></a>CGopherConnection::CGopherConnection  
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
  
### <a name="remarks"></a>Примечания  
 Никогда не создавать `CGopherConnection` напрямую. Вместо этого вызвать метод [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает `CGopherConnection` объекта и возвращает указатель на него.  
  
##  <a name="createlocator"></a>CGopherConnection::CreateLocator  
 Вызовите эту функцию-член для создания указателя gopher для поиска или определить файл на сервере gopher.  
  
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
 `pstrDisplayString`  
 Указатель на строку, содержащую имя gopher документа или папки для извлечения. Если `pstrDisplayString` параметр **NULL**, возвращается каталог по умолчанию для сервера gopher.  
  
 `pstrSelectorString`  
 Указатель на строку селектор для отправки на сервер gopher для получения элемента. `pstrSelectorString`может быть **NULL**.  
  
 *dwGopherType*  
 Указывает, является ли `pstrSelectorString` ссылается на каталог или документа, и является ли запрос gopher или gopher +. В разделе атрибуты для структуры [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pstrLocator`  
 Указатель на строку, идентифицирующую открываемого файла. Как правило, эта строка возвращается из вызова [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Указатель на строку, содержащую имя сервера gopher.  
  
 `nPort`  
 Число, определяющее порт Интернета для данного подключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Версию статической функции-члена требуется указать сервер, а версия нестатических использует имя сервера из объекта соединения.  
  
 Чтобы получить данные с сервера gopher, приложение сначала необходимо получить указатель gopher. Приложение затем следует рассматривать как непрозрачный маркер указателя (то есть приложения можно использовать указателя, но не напрямую управлять или сравнить его). Как правило, приложение использует указатель для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) функции-члена для получения конкретного набора данных.  
  
##  <a name="getattribute"></a>CGopherConnection::GetAttribute  
 Вызовите эту функцию-член для получения конкретного атрибута сведения об элементе с сервера gopher.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Параметры  
 `refLocator`  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 *strRequestedAttributes*  
 Строка разделенных пробелами, указания имен атрибутов.  
  
 `strResult`  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , получающий тип указателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может быть вызвана для определения причины ошибки.  
  
##  <a name="openfile"></a>CGopherConnection::OpenFile  
 Вызовите эту функцию-член для открытия файла на сервере gopher.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `refLocator`  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 `dwFlags`  
 Любое сочетание флагов INTERNET_FLAG_ *. В разделе [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) Дополнительные сведения о INTERNET_FLAG_\* флаги.  
  
 `pstrView`  
 Указатель на строковое представление файлов. Если существует несколько представлений файла на сервере, этот параметр определяет представления для открытия файла. Если `pstrView` — **NULL**, используется представление файлов по умолчанию.  
  
 `dwContext`  
 Идентификатор контекста для открытого файла. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CGopherFile](../../mfc/reference/cgopherfile-class.md) объекта для открытия.  
  
### <a name="remarks"></a>Примечания  
 Переопределение `dwContext` по умолчанию для идентификатора контекста параметру значение по своему выбору. Идентификатор контекста связан с этой конкретной операции `CGopherConnection` объект, созданный его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния операции, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)   
 [Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)

