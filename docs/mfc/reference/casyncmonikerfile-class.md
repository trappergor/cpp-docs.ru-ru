---
title: "Класс CAsyncMonikerFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- monikers [C++], MFC
- asynchronous controls [C++]
- CAsyncMonikerFile class
- IMoniker interface, binding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: eb8727e6fe884c98fe010beab072fb7268f2e2c4
ms.lasthandoff: 02/24/2017

---
# <a name="casyncmonikerfile-class"></a>Класс CAsyncMonikerFile
Предоставляет функции для использования асинхронных моникеров в элементах управления ActiveX (ранее элементах управления OLE).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|Создает объект `CAsyncMonikerFile`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|Закрывает и освобождает все ресурсы.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|Извлекает указатель на асинхронную передачу привязки.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|Получает формат данных в потоке.|  
|[CAsyncMonikerFile::Open](#open)|Открывает файл асинхронно.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Создает объект COM, реализующий `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Вызывается из библиотеки OLE system для получения сведений о типа привязки должен быть создан.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Вызывается из библиотеки OLE системы для получения приоритета привязки.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Вызывается для предоставления данных, как оно становится доступным для клиента во время асинхронной привязки операции.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Вызывается для отображения процесса скачивания данных.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Вызывается при запуске привязки.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Вызывается при остановке асинхронной передачи.|  
  
## <a name="remarks"></a>Примечания  
 Производный от [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), который в свою очередь является производным от [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` использует [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для доступа к любой поток данных асинхронно, включая асинхронная загрузка файлов с URL-адреса. Файлы могут быть свойства пути к данным элементов управления ActiveX.  
  
 Асинхронные моникеры используются в основном в Интернет-приложений и элементов управления ActiveX для предоставления отклика пользовательского интерфейса во время передачи файлов. Простым примером этого является использование [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронного свойства для элементов управления ActiveX. `CDataPathProperty` Объект многократно получит обратный вызов для индикации доступности новых данных exchange в процессе длительной свойство.  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в следующих статьях:  
  
- [Internet первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="a-namecasyncmonikerfilea--casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 Создает объект `CAsyncMonikerFile`.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Примечания  
 Он не создает `IBindHost` интерфейса. `IBindHost`используется только в том случае, если указать его в **откройте** функции-члена.  
  
 Описание `IBindHost` интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameclosea--casyncmonikerfileclose"></a><a name="close"></a>CAsyncMonikerFile::Close  
 Эта функция вызывается для закрыть и освободить все ресурсы.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Может быть вызван неоткрытых или уже закрытым файлы.  
  
##  <a name="a-namecreatebindstatuscallbacka--casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 Создает объект COM, реализующий `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkControlling`  
 Управление неизвестно указатель (внешний **IUnknown**) или **NULL** Если агрегат не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `pUnkControlling` не **NULL**, функция возвращает указатель на внутренний **IUnknown** на новый вспомогательного объекта COM `IBindStatusCallback`. Если `pUnkControlling` — **NULL**, функция возвращает указатель на **IUnknown** на новый вспомогательного объекта COM `IBindStatusCallback`.  
  
### <a name="remarks"></a>Примечания  
 `CAsyncMonikerFile`требуется объект COM, реализующий `IBindStatusCallback`. Реализация такого объекта MFC, и это статистическую обработку. Можно переопределить `CreateBindStatusCallback` для возврата COM-объект. COM-объект может агрегировать реализация в MFC путем вызова `CreateBindStatusCallback` с управление неизвестно COM-объекта. COM-объекты, реализованные с помощью `CCmdTarget` поддержки COM может получить управление неизвестно с помощью **CCmdTarget::GetControllingUnknown**.  
  
 Кроме того, COM-объект можно делегировать реализации MFC путем вызова **CreateBindStatusCallback (NULL)**.  
  
 [CAsyncMonikerFile::Open](#open) вызовов `CreateBindStatusCallback`.  
  
 Дополнительные сведения об асинхронных моникеров и асинхронной привязки см. в разделе [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) интерфейс и [как асинхронная привязка и хранения рабочих](http://msdn.microsoft.com/library/windows/desktop/aa379152). Обсуждение статистической обработки, в разделе [статистической обработки](http://msdn.microsoft.com/library/windows/desktop/ms686558). Все три разделов [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetbindinfoa--casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 Вызывать из клиента асинхронных моникера определить моникер асинхронной как ему нужно выполнить привязку.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Извлекает параметры для **IBindStatusCallBack**. Описание `IBindStatusCallback` интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает привязку, быть асинхронным, использовать носитель (поток), а также использовать модель принудительной отправки данных. Переопределите эту функцию, если вы хотите изменить поведение привязки.  
  
 Одна из причин для этого следует привязать с помощью модели по запросу данных вместо модели принудительной отправки данных. В модели данных запросу клиента дисков операции привязки и моникер может только передавать данные клиенту при его считывании. В модели принудительной отправки данных моникер накопители операцию асинхронной привязки и постоянно уведомляет клиента, каждый раз, когда новые данные недоступны.  
  
##  <a name="a-namegetbindinga--casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 Эта функция вызывается для получения указатель на асинхронную передачу привязки.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IBinding` интерфейса, предоставляемого после начала асинхронной передачи. Возвращает **NULL** Если для какой-либо причине невозможно сделать передачу асинхронно.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет контролировать процесс с помощью передачи данных `IBinding` интерфейса, например, с **IBinding::Abort**, **IBinding::Pause**, и **IBinding::Resume**.  
  
 Описание `IBinding` интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetformatetca--casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 Эта функция вызывается для получения формат данных в потоке.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру Windows [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) открытое потока. Возвращает **NULL** моникер не привязан, если он не является асинхронной, или не было начато асинхронной операции.  
  
##  <a name="a-namegetprioritya--casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 Вызываемой клиентом асинхронной моникера, как начнется процесс привязки получают приоритет потока для операции привязки.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приоритет, по которому асинхронная передача будет выполняться. Один из флагов приоритета стандартных потоков: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, и **THREAD_PRIORITY_TIME_CRITICAL**. Функции Windows в разделе [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) для описания этих значений.  
  
### <a name="remarks"></a>Примечания  
 `GetPriority`не должен вызываться напрямую. **THREAD_PRIORITY_NORMAL** возвращается в реализации по умолчанию.  
  
##  <a name="a-nameondataavailablea--casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 Вызывает асинхронный моникер `OnDataAvailable` для предоставления данных клиенту, когда они становятся доступными, во время асинхронной привязки операции.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Параметры  
 `dwSize`  
 Совокупное количество (в байтах) данных, доступных с начала привязки. Может равняться нулю, указывающее, что объем данных, не относящиеся к операции или что не конкретную сумму стала доступной.  
  
 *bscfFlag*  
 Объект **BSCF** значение перечисления. Может иметь одно или несколько из следующих значений:  
  
- **BSCF_FIRSTDATANOTIFICATION** идентифицирует первый вызов `OnDataAvailable` для операции данной привязки.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** определяет промежуточных вызов `OnDataAvailable` для операции привязки.  
  
- **BSCF_LASTDATANOTIFICATION** определяет последний вызов `OnDataAvailable` для операции привязки.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. Образец реализации см.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWinInet&#5;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="a-nameonlowresourcea--casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 Моникер вызывается, когда не хватает ресурсов.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `GetBinding( )-> Abort( )`.  
  
##  <a name="a-nameonprogressa--casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 Вызывается моникером несколько раз, чтобы указать текущий ход выполнения этой операции привязки, обычно в разумные интервалы во время продолжительной операции.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Параметры  
 `ulProgress`  
 Указывает текущий ход выполнения операции привязки относительно ожидаемого максимума, указанного в `ulProgressMax`.  
  
 `ulProgressMax`  
 Указывает ожидаемое максимальное значение `ulProgress` во время вызовов `OnProgress` для этой операции.  
  
 `ulStatusCode`  
 Дополнительные сведения о ходе выполнения операции привязки. Допустимые значения берутся из `BINDSTATUS` перечисления. Возможные значения см.  
  
 `szStatusText`  
 Сведения о текущих, в зависимости от значения `ulStatusCode`. Возможные значения см.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения для `ulStatusCode` (и `szStatusText` для каждого значения) являются:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 Находит ресурс, который содержит объект или хранилища, привязанными к операции привязки. `szStatusText` Содержит отображаемое имя ресурса, в которой выполняется поиск для (например, «www.microsoft.com»).  
  
 **BINDSTATUS_CONNECTING**  
 Операция привязки — подключение к ресурсу, который содержит объект или хранилища, привязанным к. `szStatusText` Содержит отображаемое имя подключения (например, IP-адреса) для ресурса.  
  
 **BINDSTATUS_SENDINGREQUEST**  
 Операция привязки запрашивает объект или хранилища, привязанным к. `szStatusText` Содержит отображаемое имя объекта (например, имя файла).  
  
 **BINDSTATUS_REDIRECTING**  
 Операции привязки был перенаправлен в расположение различных данных. `szStatusText` Содержит отображаемое имя нового расположения данных.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 Операция привязки Получает запрашиваемый объект или хранилища из кэшированную копию. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 Операция привязки было начато получение объекта или хранилища, привязанным к. `szStatusText` Содержит отображаемое имя расположения данных.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 Операция привязки продолжает получать объект или хранилища, привязанным к. `szStatusText` Содержит отображаемое имя расположения данных.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 Операция привязки Завершено получение объекта или хранилища, привязанным к. `szStatusText` Содержит отображаемое имя расположения данных.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 Экземпляр объекта, привязываемого к собирается только создаваться. `szStatusText` Предоставляет CLSID нового объекта в строковом формате, после чего клиент возможность отмены операции привязки, при необходимости.  
  
##  <a name="a-nameonstartbindinga--casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 Переопределите эту функцию в производных классах, чтобы выполнять действия при запуске привязки.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается моникером. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="a-nameonstopbindinga--casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 Вызывается в конце операции привязки моникера.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Параметры  
 `hresult`  
 `HRESULT` Именно ошибки или предупреждения.  
  
 *szErrort*  
 Строка описания ошибки.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для выполнения действий при остановке передачи. По умолчанию функция освобождает `IBinding`.  
  
 Описание `IBinding` интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameopena--casyncmonikerfileopen"></a><a name="open"></a>CAsyncMonikerFile::Open  
 Вызовите эту функцию-член для открытия файла асинхронно.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 Указатель на файл, открываемый асинхронно. Файл может быть любой допустимый URL-адрес или имя файла.  
  
 `pError`  
 Указатель на файл исключения. В случае возникновения ошибки он будет присвоено причину.  
  
 `pMoniker`  
 Указатель на интерфейс асинхронного моникер `IMoniker`, точное моникер, который представляет собой сочетание моникера документа собственные можно получить с **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**и специальное имя, созданное из имени пути. Элемент управления можно использовать этот моникер для привязки, но это не моникер, следует сохранить элемент управления.  
  
 *pBindHost*  
 Указатель на `IBindHost` интерфейс, который будет использоваться для создания специального имени из потенциально относительным путем. Если привязка узла является недопустимым или не имеет специальное имя, по умолчанию используется вызов **Open (** `lpszFileName` **,**`pError`**)**. Описание `IBindHost` интерфейса см. в разделе [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pServiceProvider`  
 Указатель на `IServiceProvider` интерфейса. Если поставщик услуг недопустим или не предоставляет службы для `IBindHost`, по умолчанию используется вызов **Open (** `lpszFileName` **,**`pError`**)**.  
  
 *pUnknown*  
 Указатель на **IUnknown** интерфейса. Если `IServiceProvider` найден, функция запрашивает `IBindHost`. Если поставщик услуг недопустим или не предоставляет службы для `IBindHost`, по умолчанию используется вызов **Open (** `lpszFileName` **,**`pError`**)**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если файл открыт успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов запускает процесс привязки.  
  
 Можно использовать URL-адрес или имя файла для `lpszURL` параметр. Например:  
  
 [!code-cpp[NVC_MFCWinInet №&6;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 — или —  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)   
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

