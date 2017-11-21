---
title: "Класс CAsyncMonikerFile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs: C++
helpviewer_keywords:
- CAsyncMonikerFile [MFC], CAsyncMonikerFile
- CAsyncMonikerFile [MFC], Close
- CAsyncMonikerFile [MFC], GetBinding
- CAsyncMonikerFile [MFC], GetFormatEtc
- CAsyncMonikerFile [MFC], Open
- CAsyncMonikerFile [MFC], CreateBindStatusCallback
- CAsyncMonikerFile [MFC], GetBindInfo
- CAsyncMonikerFile [MFC], GetPriority
- CAsyncMonikerFile [MFC], OnDataAvailable
- CAsyncMonikerFile [MFC], OnLowResource
- CAsyncMonikerFile [MFC], OnProgress
- CAsyncMonikerFile [MFC], OnStartBinding
- CAsyncMonikerFile [MFC], OnStopBinding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de31d57f3b9724cf8a3075b34be45a21556aea2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|Создает объект COM, который реализует `IBindStatusCallback`.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|Вызывается средой библиотеки OLE системы для получения сведений о типа привязки должен быть создан.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|Вызывается средой библиотеки OLE системы для получения приоритет привязки.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|Вызывается для предоставления данных, как он становится доступным для клиента во время операций асинхронной привязки.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|Вызывается для отображения процесса скачивания данных.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|Вызывается, когда начинается привязка.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|Вызывается, когда асинхронная передача остановлена.|  
  
## <a name="remarks"></a>Примечания  
 Производный от [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), который в свою очередь является производным от [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` использует [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для доступа к любой поток данных асинхронно в том числе асинхронная загрузка файлов с URL-адреса. Файлы могут быть свойства пути к данным элементов управления ActiveX.  
  
 Асинхронные моникеры используются главным образом в Интернет-приложений и элементов управления ActiveX для обеспечения быстрого реагирования пользовательского интерфейса во время передачи файлов. Простым примером этого является использование [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) для предоставления асинхронных свойств для элементов управления ActiveX. `CDataPathProperty` Объект многократно получит обратный вызов для указания доступности новых данных появляется в процессе обмена свойство длительное время.  
  
 Дополнительные сведения о способах использования асинхронных моникеров и элементы управления ActiveX в веб-приложений см. в следующих статьях:  
  
- [Интернете первые шаги: Асинхронные моникеры](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [Интернете первые шаги: Элементы управления ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 Создает объект `CAsyncMonikerFile`.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>Примечания  
 Он не создает `IBindHost` интерфейса. `IBindHost`используется только в том случае, если указать его в **откройте** функции-члена.  
  
 Описание `IBindHost` интерфейсом, см. в Windows SDK.  
  
##  <a name="close"></a>CAsyncMonikerFile::Close  
 Вызывайте эту функцию, чтобы закрыть и освободить все ресурсы.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Примечания  
 Может быть вызван файлы неоткрытый или уже закрыт.  
  
##  <a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 Создает объект COM, который реализует `IBindStatusCallback`.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkControlling`  
 Указатель на управляющий unknown (внешнего **IUnknown**) или **NULL** Если агрегат не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если `pUnkControlling` не **NULL**, функция возвращает указатель на внутренний **IUnknown** на новый вспомогательного объекта COM `IBindStatusCallback`. Если `pUnkControlling` — **NULL**, функция возвращает указатель на **IUnknown** на новый вспомогательного объекта COM `IBindStatusCallback`.  
  
### <a name="remarks"></a>Примечания  
 `CAsyncMonikerFile`требуется объект COM, реализующий `IBindStatusCallback`. MFC реализует такого объекта, и он не статистическую обработку. Можно переопределить `CreateBindStatusCallback` для возврата COM-объект. COM-объект может агрегировать реализации MFC путем вызова `CreateBindStatusCallback` с управляющий unknown COM-объекта. COM-объекты, реализованные с помощью `CCmdTarget` поддержка COM можно получить, управляющий Неизвестный с помощью **CCmdTarget::GetControllingUnknown**.  
  
 Кроме того, COM-объект можно делегировать реализацию MFC путем вызова **CreateBindStatusCallback (NULL)**.  
  
 [CAsyncMonikerFile::Open](#open) вызовов `CreateBindStatusCallback`.  
  
 Дополнительные сведения об асинхронных моникеров и асинхронные привязки см. в разделе [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) интерфейс и [как асинхронной привязки и хранилища рабочих](http://msdn.microsoft.com/library/windows/desktop/aa379152). Обсуждение статистической обработки, см. в разделе [статистической обработки](http://msdn.microsoft.com/library/windows/desktop/ms686558). Все три темы также в Windows SDK.  
  
##  <a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 Вызванный из клиентского асинхронной моникера сообщить асинхронной моникер как ему нужно выполнить привязку.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Получает настройки для **IBindStatusCallBack**. Описание `IBindStatusCallback` интерфейсом, см. в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает привязку, выполняться асинхронно, чтобы использовать носитель (поток) и использовать модель принудительной отправки данных. Переопределите эту функцию, если вы хотите изменить поведение привязки.  
  
 Одна из причин для этого следует привязать с помощью модели по запросу данных вместо принудительной отправки данных модели. В модели данных запросу клиента диски при выполнении операции привязки, и специальное имя только предоставляет данные клиенту при чтении. В модель принудительной отправки данных моникер диски при выполнении операции асинхронной привязки и постоянно уведомляет клиента всякий раз, когда станут доступны новые данные.  
  
##  <a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 Вызывайте эту функцию, чтобы получить указатель на асинхронную передачу привязки.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IBinding` интерфейс, предоставляемый, когда начинается асинхронная передача. Возвращает **NULL** Если для какой-либо причине невозможно сделать передачу асинхронно.  
  
### <a name="remarks"></a>Примечания  
 Это позволяет контролировать процесс посредством передачи данных `IBinding` интерфейса, например, с **IBinding::Abort**, **IBinding::Pause**, и **IBinding::Resume**.  
  
 Описание `IBinding` интерфейсом, см. в Windows SDK.  
  
##  <a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 Эта функция вызывается для получения формат данных в потоке.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на структуру Windows [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) для открытым в данный момент поток. Возвращает **NULL** если моникер не привязан, если он не является асинхронным, или если асинхронная операция не было начато.  
  
##  <a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 Вызывается клиентом асинхронной моникер, когда начинается процесс привязки для получения приоритет потока для привязки операции.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Приоритет, когда асинхронная передача будет выполняться. Один из флагов приоритет стандартных потоков: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**,  **THREAD_PRIORITY_IDLE**, **всех**, **THREAD_PRIORITY_NORMAL**, и **THREAD_PRIORITY_TIME_CRITICAL**. В описании функции Windows [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) описание этих значений.  
  
### <a name="remarks"></a>Примечания  
 `GetPriority`не должен вызываться напрямую. **THREAD_PRIORITY_NORMAL** возвращается посредством реализации по умолчанию.  
  
##  <a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 Вызывает асинхронный моникер `OnDataAvailable` для предоставления данных клиенту, как они станут доступны, во время асинхронной привязки операции.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>Параметры  
 `dwSize`  
 Совокупное количество (в байтах) данных, доступных с начала выполнения привязки. Может быть 0, указывающее, что объем данных, не имеет отношения к операции или, не определенное стал доступен.  
  
 *bscfFlag*  
 Объект **BSCF** значение перечисления. Может иметь одно или несколько из следующих значений:  
  
- **BSCF_FIRSTDATANOTIFICATION** идентифицирует первый вызов `OnDataAvailable` для выполнения операции данной привязки.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** идентифицирует промежуточных вызов `OnDataAvailable` для операции привязки.  
  
- **BSCF_LASTDATANOTIFICATION** идентифицирует последнего вызова `OnDataAvailable` для операции привязки.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию этой функции не выполняет никаких действий. См. приведенный ниже пример реализации интерфейса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWinInet#5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 Вызывается средой моникер, когда не хватает ресурсов.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию вызывает `GetBinding( )-> Abort( )`.  
  
##  <a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 Вызывается несколько раз, чтобы указать текущий ход выполнения этой операции bind, обычно в разумные интервалы во время продолжительной операции специальным именем.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>Параметры  
 `ulProgress`  
 Указывает текущее состояние привязки операции относительно ожидаемого максимума, указанного в `ulProgressMax`.  
  
 `ulProgressMax`  
 Указывает ожидаемое максимальное значение параметра `ulProgress` для длительность вызовов `OnProgress` для этой операции.  
  
 `ulStatusCode`  
 Дополнительные сведения о ходе выполнения операции привязки. Допустимые значения берутся из `BINDSTATUS` перечисления. Возможные значения см. заметки.  
  
 `szStatusText`  
 Сведения о текущей работе, в зависимости от значения `ulStatusCode`. Возможные значения см. заметки.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `ulStatusCode` (и `szStatusText` для каждого значения) являются:  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 Находит ресурс, который содержит объект или хранилища, которая привязывается к операции привязки. `szStatusText` Предоставляет отображаемое имя ресурса, в которой выполняется поиск для (например, «www.microsoft.com»).  
  
 **BINDSTATUS_CONNECTING**  
 Ресурс, который содержит объект или хранилища, которая привязывается к подключается при выполнении операции привязки. `szStatusText` Предоставляет отображаемое имя ресурса подключения (например, IP-адрес).  
  
 **BINDSTATUS_SENDINGREQUEST**  
 При выполнении операции привязки запрашивает объект или хранилища, которая привязывается к. `szStatusText` Предоставляет отображаемое имя объекта (например, имя файла).  
  
 **BINDSTATUS_REDIRECTING**  
 При выполнении операции привязки был перенаправлен в расположение различных данных. `szStatusText` Предоставляет отображаемое имя нового расположения данных.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 При выполнении операции привязки Получает запрашиваемый объект или хранилища из кэшированную копию. `szStatusText` — **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 При выполнении операции привязки было начато получение объекта или хранилища, которая привязывается к. `szStatusText` Предоставляет отображаемое имя расположения данных.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 Для получения объекта или хранилища, которая привязывается к продолжается при выполнении операции привязки. `szStatusText` Предоставляет отображаемое имя расположения данных.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 При выполнении операции привязки Завершено получение объекта или хранилища, которая привязывается к. `szStatusText` Предоставляет отображаемое имя расположения данных.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 Экземпляр объекта, которая привязывается к собирается только создать. `szStatusText` Предоставляет CLSID нового объекта в строковом формате, после чего клиент возможность отменить операцию привязки, при необходимости.  
  
##  <a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 Переопределите эту функцию в производных классах, чтобы выполнять действия при запуске привязки.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается специальным именем. Реализация по умолчанию не выполняет никаких действий.  
  
##  <a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 Вызывается в конце операции привязки моникера.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>Параметры  
 `hresult`  
 `HRESULT` , Ошибки или предупреждения.  
  
 *szErrort*  
 Строка символов, описывающее ошибку.  
  
### <a name="remarks"></a>Примечания  
 Переопределите эту функцию для выполнения действий, когда передача остановилась. По умолчанию функция освобождает `IBinding`.  
  
 Описание `IBinding` интерфейсом, см. в Windows SDK.  
  
##  <a name="open"></a>CAsyncMonikerFile::Open  
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
 Указатель на файл должен быть открыт асинхронно. Файл может быть любой допустимый URL-адрес или имя файла.  
  
 `pError`  
 Указатель на файл исключения. В случае ошибки он будет присвоено причину.  
  
 `pMoniker`  
 Указатель на интерфейс асинхронной моникер `IMoniker`, точное моникер, — это сочетание моникер документа собственные, которое можно получить с **IOleClientSite::GetMoniker (** *OLEWHICHMK_ КОНТЕЙНЕР* **)**и специальное имя, созданное из имени пути. Для привязки элемента управления можно использовать этот моникер, но это не моникер, следует сохранить элемент управления.  
  
 *pBindHost*  
 Указатель на `IBindHost` интерфейс, который будет использоваться для создания моникер от потенциально относительного пути. Если привязки узла является недопустимым или не обеспечивает специальное имя, по умолчанию используется вызов **Open (** `lpszFileName` **,**`pError`**)**. Описание `IBindHost` интерфейсом, см. в Windows SDK.  
  
 `pServiceProvider`  
 Указатель на `IServiceProvider` интерфейса. Если поставщик услуг недопустим или не удается предоставить службу для `IBindHost`, по умолчанию — вызов **Open (** `lpszFileName` **,**`pError`**)**.  
  
 *pUnknown*  
 Указатель на **IUnknown** интерфейса. Если `IServiceProvider` найден, функция запрашивает `IBindHost`. Если поставщик услуг недопустим или не удается предоставить службу для `IBindHost`, по умолчанию — вызов **Open (** `lpszFileName` **,**`pError`**)**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если файл открыт успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Этот вызов инициирует процесс привязки.  
  
 Можно использовать URL-адрес или имя файла для `lpszURL` параметра. Пример:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - или  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMonikerFile](../../mfc/reference/cmonikerfile-class.md)   
 [Класс CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)
