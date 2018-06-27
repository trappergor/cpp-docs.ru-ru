---
title: Класс CGopherConnection | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49fe725c700a46e59625289de7ca5edf4b4d25b2
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955691"
---
# <a name="cgopherconnection-class"></a>Класс CGopherConnection
Управление подключением к интернет-серверу gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены являются устаревшими, так как они не работают на платформе Windows XP, но они будут продолжать работать на более старых платформ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Создает объект `CGopherConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CGopherConnection::CreateLocator](#createlocator)|Создает [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объект для поиска файлов на сервере gopher.|  
|[CGopherConnection::GetAttribute](#getattribute)|Возвращает атрибут информацию об объекте gopher.|  
|[CGopherConnection::OpenFile](#openfile)|Открывает файл gopher.|  
  
## <a name="remarks"></a>Примечания  
 Служба gopher является одним из трех служб Интернета, распознаваемые классов MFC WinInet.  
  
 Класс `CGopherConnection` содержит конструктор и трех дополнительных функции-члена, управлять службой gopher: [OpenFile](#openfile), [CreateLocator](#createlocator), и [GetAttribute](#getattribute).  
  
 Для связи с Интернет-серверу gopher, необходимо создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а затем вызвать [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), создающем `CGopherConnection` объект и возвращает указатель на него. Никогда не создавайте `CGopherConnection` объекта напрямую.  
  
 Дополнительные сведения о том, как `CGopherConnection` работает с другими классами MFC Интернет, см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md). Дополнительные сведения об использовании двух других поддерживаемых служб Интернета, FTP и HTTP. в разделе классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [классе CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
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
 *pSession*  
 Указатель на связанный [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.  
  
 *hConnected*  
 Дескриптор Windows текущего сеанса Интернета.  
  
 *pstrServer*  
 Указатель на строку, содержащую имя FTP-сервера.  
  
 *dwContext*  
 Идентификатор контекста для операции. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию имеет значение 1; Тем не менее можно явно назначить идентификатор контекста для операции. Объект, а вся работа, она будет связана с этим идентификатором контекста.  
  
 *pstrUserName*  
 Указатель на строку с завершающим нулем, указывающее имя пользователя для входа. Если **NULL**, значение по умолчанию является анонимным.  
  
 *pstrPassword*  
 Указатель символом null строку, которая указывает пароль, используемый для входа. Если оба *pstrPassword* и *pstrUserName* , **NULL**, анонимных паролей по умолчанию является имя электронной почты пользователя. Если *pstrPassword* — **NULL** (или пустую строку), но *pstrUserName* не **NULL**, используется пустой пароль. В следующей таблице описаны поведение для четыре возможные параметры *pstrUserName* и *pstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|Имя пользователя, отправленных FTP-сервер|Пароль, отправленных FTP-сервер|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**Значение NULL** или «»|**Значение NULL** или «»|«anonymous»|Имя электронной почты пользователя|  
|Не- **NULL** строки|**Значение NULL** или «»|*pstrUserName*|" "|  
|**Значение NULL** отличных **NULL** строки|**ОШИБКА**|**ОШИБКА**||  
|Не- **NULL** строки|Не- **NULL** строки|*pstrUserName*|*pstrPassword*|  
  
 *nPort*  
 Число, определяющее порт TCP/IP, используемый на сервере.  
  
### <a name="remarks"></a>Примечания  
 Никогда не создавайте `CGopherConnection` напрямую. Вместо этого вызовите [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), которая создает `CGopherConnection` объекта и возвращает указатель на него.  
  
##  <a name="createlocator"></a>  CGopherConnection::CreateLocator  
 Вызовите эту функцию-член для создания локатора gopher для поиска или определить файл на сервере gopher.  
  
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
 *pstrDisplayString*  
 Указатель на строку, содержащую имя gopher документа или папки должны быть получены. Если *pstrDisplayString* параметр **NULL**, возвращается каталог по умолчанию для сервера gopher.  
  
 *pstrSelectorString*  
 Указатель на строку селектор должно отправляться gopher-сервер, чтобы получить элемент. *pstrSelectorString* может быть **NULL**.  
  
 *dwGopherType*  
 Указывает, является ли *pstrSelectorString* ссылается на каталог или документа, и является ли запрос gopher или gopher +. В разделе атрибуты для структуры [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) в Windows SDK.  
  
 *pstrLocator*  
 Указатель на строку, идентифицирующую открываемый файл. Как правило, эта строка возвращается из вызова [CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Указатель на строку, содержащую имя сервера gopher.  
  
 *nPort*  
 Номер, идентифицирующий Интернет порт для этого подключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
### <a name="remarks"></a>Примечания  
 Статические версию функции-члена требуется указать сервер, а версии нестатических использует имя сервера из объекта соединения.  
  
 Чтобы получить данные с сервера gopher, приложение сначала необходимо получить указатель gopher. Приложение затем следует рассматривать как непрозрачный маркер локатора (т. е приложения можно использовать локатора, но не напрямую управлять или сравнить ее). Как правило, приложение использует локатор для вызовов [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) функция-член для извлечения конкретные сведения.  
  
##  <a name="getattribute"></a>  CGopherConnection::GetAttribute  
 Вызовите эту функцию-член для извлечения конкретного атрибута сведения об элементе с сервера gopher.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Параметры  
 *refLocator*  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 *strRequestedAttributes*  
 Пробелами строка, указывающая имена атрибутов.  
  
 *strResult*  
 Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) , получающий тип указателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0. При сбое вызова функции Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) может вызвать, чтобы определить причину ошибки.  
  
##  <a name="openfile"></a>  CGopherConnection::OpenFile  
 Вызовите эту функцию-член для открытия файла на сервере gopher.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 *refLocator*  
 Ссылку на [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) объекта.  
  
 *dwFlags*  
 Любое сочетание флагов INTERNET_FLAG_ *. В разделе [CInternetSession::OpenUrl](../../mfc/reference/cinternetsession-class.md#openurl) для получения дополнительных сведений о INTERNET_FLAG_\* флаги.  
  
 *pstrView*  
 Указатель на строку представления файла. Если существует несколько представлений файла на сервере, этот параметр определяет представления для открытия файла. Если *pstrView* — **NULL**, используется представление по умолчанию файл.  
  
 *dwContext*  
 Идентификатор контекста для открытого файла. В разделе **примечания** Дополнительные сведения о *dwContext*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CGopherFile](../../mfc/reference/cgopherfile-class.md) объект должен быть открыт.  
  
### <a name="remarks"></a>Примечания  
 Переопределить *dwContext* по умолчанию для идентификатора контекста присвоено значение по своему выбору. Идентификатор контекста связан с этой определенной операции `CGopherConnection` объектом, созданным с его [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта. Возвращаемое значение на [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние операции, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
## <a name="see-also"></a>См. также  
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс классе CFtpConnection](../../mfc/reference/cftpconnection-class.md)   
 [Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)   
 [Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)   
 [Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)   
 [Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
