---
title: "Класс CBindStatusCallback | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
caps.latest.revision: 22
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 50a0a27528f402cda5906658cd2c9cf57a5908e8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cbindstatuscallback-class"></a>Класс CBindStatusCallback
Этот класс реализует интерфейс `IBindStatusCallback`.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Ваш класс, содержащий функцию, которая будет вызываться при получении данных.  
  
 *nBindFlags*  
 Задает флаги привязки, которые возвращаются [GetBindInfo](#getbindinfo). Реализация по умолчанию задает привязку, быть асинхронным, извлекает последнюю версию данных и не сохраняет полученные данные кэша на диске.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Конструктор.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Создает статический метод, который запускает процесс загрузки `CBindStatusCallback` и вызывает `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Вызывается асинхронный моникера для получения сведений о типа привязки должен быть создан.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Вызывается асинхронный моникера для получения приоритет операции привязки. Возвращает реализацию ATL `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Вызывается для предоставления данных в приложение, как она станет доступной. Считывает данные, а затем вызывает функцию, переданный ему для использования данных.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Вызывается асинхронный моникером для передачи указателя на интерфейс объекта приложения. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Вызывается для отображения хода процесса скачивания данных. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Вызывается при запуске привязки.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Вызывается при остановке асинхронную передачу данных.|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Инициализирует доступные байты и прочитано байтов до нуля, создает объект типа push потока из URL-адреса и вызывает `OnDataAvailable` каждый раз данные недоступны.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Число байтов, доступных для чтения.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Общее число считанных байтов.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Указатель на функцию вызывается, когда данные недоступны.|  
|[CBindStatusCallback::m_pT](#m_pt)|Указатель на объект, который запрашивает асинхронную передачу данных.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Указатель на [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) интерфейс для текущей операции привязки.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Указатель на `IBinding` интерфейс для текущей операции привязки.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Указатель на [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для URL-адрес.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейс для передачи данных.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CBindStatusCallback` реализует интерфейс `IBindStatusCallback`. `IBindStatusCallback`должен быть реализован приложением, поэтому он может получать уведомления от асинхронную передачу данных. Использует асинхронный моникера, предоставляемый системой `IBindStatusCallback` методы для отправки и получения сведений об асинхронных данных переноса в и из объекта.  
  
 Как правило `CBindStatusCallback` объект связан с операции конкретной привязки. Например, в [ASYNC](../../visual-cpp-samples.md) пример, при установке свойства URL-адрес, он создает `CBindStatusCallback` объекта в вызове `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing&#86;](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Асинхронные моникер использует функцию обратного вызова `OnData` для вызова приложения при получении данных. Моникер асинхронной предоставляется системой.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback  
 Конструктор.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Примечания  
 Создает объект для получения уведомлений о асинхронную передачу данных. Как правило один объект создается для каждой операции привязки.  
  
 Конструктор также инициализирует [m_pT](#m_pt) и [m_pFunc](#m_pfunc) для **NULL**.  
  
##  <a name="dtor"></a>CBindStatusCallback:: ~ CBindStatusCallback  
 Деструктор  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="download"></a>CBindStatusCallback::Download  
 Создает `CBindStatusCallback` и вызывает `StartAsyncDownload` для запуска асинхронную загрузку данных из указанного URL-адреса.  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, который запрашивает асинхронную передачу данных. `CBindStatusCallback` Объектов шаблонизируется класс этого объекта.  
  
 *pFunc*  
 [in] Указатель на функцию, который получает данные, считываемые. Функция является членом класса объекта типа `T`. В разделе [StartAsyncDownload](#startasyncdownload) синтаксис и примеры.  
  
 `bstrURL`  
 [in] URL-адрес для получения данных. Может быть любой допустимый URL-адрес или имя файла. Не может быть **NULL**. Например:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** контейнера. **Значение NULL,** по умолчанию.  
  
 `bRelative`  
 [in] Флаг, указывающий, является ли URL относительным или абсолютным. **Значение FALSE,** по умолчанию, то есть URL-адрес является абсолютным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Каждый раз при наличии данных отправляется к объекту через `OnDataAvailable`. `OnDataAvailable`Считывает данные и вызывает функцию, на который указывает *pFunc* (например, для хранения данных, или распечатайте его на экране).  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 Вызывается, чтобы определить способ привязки моникера.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pgrfBSCF*  
 [out] Указатель на **BINDF** значений перечисления, определяющее, как должно выполняться операции привязки. По умолчанию значение с помощью следующих значений перечисления:  
  
 **BINDF_ASYNCHRONOUS** асинхронной загрузки.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` возвращает **E_PENDING** при данных еще не доступен вместо блокировки, пока данные не доступны.  
  
 **BINDF_GETNEWESTVERSION** операции привязки следует получить последнюю версию данных.  
  
 **BINDF_NOWRITECACHE** операции привязки не следует хранить полученные данные кэша на диске.  
  
 *pbindinfo*  
 [in, out] Указатель на **BINDINFO** структура предоставляет дополнительную информацию о как объект хочет привязки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает привязку асинхронным и использование модели принудительной отправки данных. В модели принудительной отправки данных моникер накопители операцию асинхронной привязки и постоянно уведомляет клиента, каждый раз, когда новые данные недоступны.  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 Вызывается асинхронный моникера для получения приоритет операции привязки.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Параметры  
 *pnPriority*  
 [out] Адрес **ДЛИННЫЕ** переменную, которая, в случае успешного выполнения получает приоритет.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
##  <a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead  
 Можно использовать для хранения числа байтов, доступных для чтения.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Примечания  
 Инициализируются с нулем в `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 Общее количество байтов, считанных в асинхронную передачу данных.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Примечания  
 Увеличивается на единицу при каждом `OnDataAvailable` вызывается на число фактически считанных байтов. Инициализируются с нулем в `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>CBindStatusCallback::m_pFunc  
 Функция, на который указывает `m_pFunc` вызывается `OnDataAvailable` после считывания доступные данные (например, для хранения данных, или распечатайте его на экране).  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Примечания  
 Функция, на который указывает `m_pFunc` является членом класса объекта и имеет следующий синтаксис:  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>CBindStatusCallback::m_pT  
 Указатель на объект, который запрашивает асинхронную передачу данных.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Примечания  
 `CBindStatusCallback` Объектов шаблонизируется класс этого объекта.  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 Указатель на [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) интерфейс, обеспечивающий доступ к контексту привязки (объекта, сохраняет сведения об операции привязки моникера определенного).  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Примечания  
 Инициализируется в `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>CBindStatusCallback::m_spBinding  
 Указатель на `IBinding` интерфейса текущей операции привязки.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Примечания  
 Инициализируется в `OnStartBinding` и выпуска в `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 Указатель на [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для URL-адрес.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Примечания  
 Инициализируется в `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>CBindStatusCallback::m_spStream  
 Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейса текущей операции привязки.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Примечания  
 Инициализируется в `OnDataAvailable` из **STGMEDIUM** структуры при **BCSF** установлен флаг **BCSF_FIRSTDATANOTIFICATION** и освободить после **BCSF** установлен флаг **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 Вызовов асинхронных моникеров, предоставляемых системой `OnDataAvailable` предоставлять данные для объекта, когда они становятся доступными.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>Параметры  
 *grfBSCF*  
 [in] Объект **BSCF** значение перечисления. Один или несколько из следующих действий: **BSCF_FIRSTDATANOTIFICATION**, **BSCF_INTERMEDIARYDATANOTIFICATION**, или **BSCF_LASTDATANOTIFICATION**.  
  
 `dwSize`  
 [in] Совокупное количество (в байтах) данных, доступных с начала привязки. Может быть&0;, обозначающего объем данных, не имеет значения или что не конкретную сумму стала доступной.  
  
 *pFormatEtc*  
 [in] Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) структуру, содержащую формат доступных данных. Если формат не может быть **CF_NULL**.  
  
 *pstgmed*  
 [in] Указатель на [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) структура, которая содержит фактические данные теперь доступна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 `OnDataAvailable`Считывает данные, а затем вызывает метод класса объекта (например, для хранения данных, или распечатайте его на экране). В разделе [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) подробные сведения.  
  
##  <a name="onlowresource"></a>CBindStatusCallback::OnLowResource  
 Вызывается, когда не хватает ресурсов.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 Зарезервировано.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable  
 Вызывается асинхронный моникером для передачи указателя на интерфейс объекта приложения.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор запрашиваемого интерфейса. Не используется.  
  
 `punk`  
 Адрес интерфейса IUnknown. Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="onprogress"></a>CBindStatusCallback::OnProgress  
 Вызывается для отображения хода процесса скачивания данных.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>Параметры  
 `ulProgress`  
 Длинное целое без знака. Не используется.  
  
 `ulProgressMax`  
 Длинное целое без знака не используется.  
  
 `ulStatusCode`  
 Длинное целое без знака. Не используется.  
  
 `szStatusText`  
 Адрес строковое значение. Не используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding  
 Задает элемент [m_spBinding](#m_spbinding) для `IBinding` указателя в `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 Зарезервировано для будущего использования.  
  
 `pBinding`  
 [in] Операция привязки адреса интерфейса IBinding текущего. Это не может быть NULL. Клиент должен вызывать метод AddRef для этого указателя, чтобы сохранить ссылку на объект привязки.  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 Выпуски `IBinding` указателя на член данных [m_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Параметры  
 `hresult`  
 Код состояния возвращается из операции привязки.  
  
 szStatusText  
 Адрес строковое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Вызывается асинхронных моникеров, предоставляемых системой для обозначения конца операции привязки.  
  
##  <a name="startasyncdownload"></a>CBindStatusCallback::StartAsyncDownload  
 Начинает асинхронную загрузку данных из указанного URL-адреса.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 [in] Указатель на объект, который запрашивает асинхронную передачу данных. `CBindStatusCallback` Объектов шаблонизируется класс этого объекта.  
  
 *pFunc*  
 [in] Указатель на функцию, которая получает считываемых данных. Функция является членом класса объекта типа `T`. В разделе **примечания** синтаксис и примеры.  
  
 `bstrURL`  
 [in] URL-адрес для получения данных. Может быть любой допустимый URL-адрес или имя файла. Не может быть **NULL**. Пример:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** контейнера. **Значение NULL,** по умолчанию.  
  
 `bRelative`  
 [in] Флаг, указывающий, является ли URL относительным или абсолютным. **Значение FALSE,** по умолчанию, то есть URL-адрес является абсолютным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Каждый раз при наличии данных отправляется к объекту через `OnDataAvailable`. `OnDataAvailable`Считывает данные и вызывает функцию, на который указывает *pFunc* (например, для хранения данных, или распечатайте его на экране).  
  
 Функция, на который указывает *pFunc* является членом класса объекта и имеет следующий синтаксис:  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 В следующем примере (берется из [ASYNC](../../visual-cpp-samples.md) образца), функция `OnData` записывает полученные данные в текстовом поле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#87;](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

