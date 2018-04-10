---
title: Класс CBindStatusCallback | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 19aa979cb69bdbf8d74acbd96291fac9af78c845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Задает флаги привязки, которые возвращаются по [GetBindInfo](#getbindinfo). Реализация по умолчанию задает привязку асинхронным, извлекает последнюю версию данных или объект и не сохраняет полученные данные кэша на диске.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Конструктор.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Создает статический метод, который запускает процесс загрузки `CBindStatusCallback` объекте и вызывает метод `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Вызывается средой асинхронной моникера для получения сведений о типа привязки должен быть создан.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Вызывается средой асинхронной моникера для получения приоритет при выполнении операции привязки. Возвращает реализацию ATL `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Вызывается для предоставления данных в приложение, как они станут доступны. Считывает данные, а затем вызывает функцию, передаваемую в его для использования данных.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Вызывается средой асинхронной моникера для передачи указателя на интерфейс объекта приложения. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Вызывается для отображения процесса скачивания данных. Возвращает реализацию ATL `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Вызывается при запуске привязки.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Вызывается при остановке асинхронную передачу данных.|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Инициализирует доступных байтов и байтов считано значение ноль, создает объект потока push-type из URL-адрес и вызывает `OnDataAvailable` каждый раз данные недоступны.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Число байтов, доступных для чтения.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Общее число считанных байтов.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Указатель на функцию вызывается, когда данные недоступны.|  
|[CBindStatusCallback::m_pT](#m_pt)|Указатель на объект, который запрашивает асинхронную передачу данных.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Указатель на [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) интерфейс для текущей операции привязки.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Указатель на `IBinding` интерфейс для текущей операции привязки.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Указатель на [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для URL-адреса для использования.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|Указатель на [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) интерфейс для передачи данных.|  
  
## <a name="remarks"></a>Примечания  
 Класс `CBindStatusCallback` реализует интерфейс `IBindStatusCallback`. `IBindStatusCallback`должен быть реализован вашим приложением, поэтому он может получать уведомления от асинхронную передачу данных. Использует асинхронную моникер, предоставляемые системой `IBindStatusCallback` методы для отправки и получения сведений о асинхронных данных передачи в и из объекта.  
  
 Как правило `CBindStatusCallback` объект связан с операцией конкретных привязку. Например, в [ASYNC](../../visual-cpp-samples.md) пример, при установке свойства URL-адрес, он создает `CBindStatusCallback` объекта в вызове `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Асинхронные моникер использует функцию обратного вызова `OnData` для вызова приложения, когда в нем данных. Моникер асинхронной предоставляется системой.  
  
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
 Создает объект для получения уведомлений о асинхронную передачу данных. Как правило один объект создается для каждой привязки операции.  
  
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
 [in] Указатель на объект запроса передачи асинхронных данных. `CBindStatusCallback` Шаблонизируется объекта класса этого объекта.  
  
 *pFunc*  
 [in] Указатель на функцию, который получает данные, считываемые. Функция является членом класса объекта типа `T`. В разделе [StartAsyncDownload](#startasyncdownload) синтаксис и примеры.  
  
 `bstrURL`  
 [in] Для получения данных из URL-адрес. Может быть любой допустимый URL-адрес или имя файла. Не может быть **NULL**. Пример:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** контейнера. **Значение NULL,** по умолчанию.  
  
 `bRelative`  
 [in] Флаг, указывающий, является ли URL-адрес относительный или абсолютный. **Значение FALSE,** по умолчанию, то есть URL-адрес является абсолютным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Каждый раз при наличии данных отправляется к объекту через `OnDataAvailable`. `OnDataAvailable`Считывает данные и вызывает функцию, на который указывает *pFunc* (например, для хранения данных, или распечатайте его на экране).  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 Вызывается, чтобы сообщить способ привязки моникера.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pgrfBSCF*  
 [out] Указатель на **BINDF** значений перечисления, указывающее, как должно выполняться при выполнении операции привязки. По умолчанию значение со следующими значениями перечисления:  
  
 **BINDF_ASYNCHRONOUS** асинхронной операции загрузки.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` возвращает **E_PENDING** при данных еще не доступен вместо блокировки, пока данные не доступны.  
  
 **BINDF_GETNEWESTVERSION** при выполнении операции привязки должны получить последнюю версию данных.  
  
 **BINDF_NOWRITECACHE** при выполнении операции привязки не следует хранить извлеченные данные кэша на диске.  
  
 *pbindinfo*  
 [in, out] Указатель на **BINDINFO** предоставляет дополнительную информацию о том, как объект хочет привязки, структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Один из стандартных `HRESULT` значения.  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию задает привязку для асинхронной и использовать модель принудительной отправки данных. В модели принудительной отправки данных моникер диски при выполнении операции асинхронной привязки и постоянно уведомляет клиента всякий раз, когда станут доступны новые данные.  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 Вызывается средой асинхронной моникера для получения приоритет при выполнении операции привязки.  
  
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
 Инициализируются с нуля `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 Общее количество байтов, прочитанных в асинхронную передачу данных.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Примечания  
 Увеличивается на единицу каждый раз `OnDataAvailable` вызывается на число фактически считанных байтов. Инициализируются с нуля `StartAsyncDownload`.  
  
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
 Указатель на объект запроса передачи асинхронных данных.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Примечания  
 `CBindStatusCallback` Шаблонизируется объекта класса этого объекта.  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 Указатель на [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) интерфейс, который предоставляет доступ к контексту привязки (объект, который хранит сведения о выполнении операции привязки моникера определенной).  
  
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
 Инициализируется в `OnStartBinding` , так и в `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 Указатель на [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) интерфейс для URL-адреса для использования.  
  
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
 Инициализируется в `OnDataAvailable` из **STGMEDIUM** структуры при **BCSF** установлен флаг **BCSF_FIRSTDATANOTIFICATION** и затем освободить после **BCSF**  установлен флаг **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 Вызовов асинхронных моникеров, предоставляемых системой `OnDataAvailable` для предоставления данных в объект, как они станут доступны.  
  
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
 [in] Совокупное количество (в байтах) данных, доступных с начала выполнения привязки. Может быть 0, указывающее, что объем данных не применимо или стали доступны, не определенное.  
  
 *pFormatEtc*  
 [in] Указатель на [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) структуру, содержащую формат доступных данных. В случае формат не может быть **CF_NULL**.  
  
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
 Вызывается средой асинхронной моникера для передачи указателя на интерфейс объекта приложения.  
  
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
 Вызывается для отображения процесса скачивания данных.  
  
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
 Задает элемент [m_spBinding](#m_spbinding) для `IBinding` указатель в `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 Зарезервировано для будущего использования.  
  
 `pBinding`  
 [in] Операция привязки адреса интерфейса IBinding текущего. Это не может быть NULL. Клиент должен вызвать метод AddRef на этот указатель, чтобы сохранить ссылку на объект привязки.  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 Выпуски `IBinding` указателя в члене данных [m_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Параметры  
 `hresult`  
 Код состояния, возвращаемые при выполнении операции привязки.  
  
 szStatusText  
 Адрес строковое значение не используется.  
  
### <a name="remarks"></a>Примечания  
 Вызывается средой системным асинхронной моникер для указания на конец операции привязки.  
  
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
 [in] Указатель на объект запроса передачи асинхронных данных. `CBindStatusCallback` Шаблонизируется объекта класса этого объекта.  
  
 *pFunc*  
 [in] Указатель на функцию, которая получает считываемые данные. Функция является членом класса объекта типа `T`. В разделе **примечания** синтаксис и примеры.  
  
 `bstrURL`  
 [in] Для получения данных из URL-адрес. Может быть любой допустимый URL-адрес или имя файла. Не может быть **NULL**. Пример:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** контейнера. **Значение NULL,** по умолчанию.  
  
 `bRelative`  
 [in] Флаг, указывающий, является ли URL-адрес относительный или абсолютный. **Значение FALSE,** по умолчанию, то есть URL-адрес является абсолютным.  
  
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
  
 В следующем примере (взяты из [ASYNC](../../visual-cpp-samples.md) образца), функция `OnData` записывает полученные данные в текстовом поле.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
