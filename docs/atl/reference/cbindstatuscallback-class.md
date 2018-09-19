---
title: Класс CBindStatusCallback | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a816d10a0cb9665938e77ae8c649464b7b6768c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108486"
---
# <a name="cbindstatuscallback-class"></a>Класс CBindStatusCallback

Этот класс реализует интерфейс `IBindStatusCallback`.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS | BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, содержащий функцию, которая будет вызываться при получении данных.

*nBindFlags*<br/>
Указывает флаги привязки, возвращаемые [GetBindInfo](#getbindinfo). Реализация по умолчанию задает привязку, чтобы асинхронными, извлекает последнюю версию данных или объекта и не сохранять извлеченные данные в дисковом кэше.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Конструктор.|
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::Download](#download)|Создает статический метод, который запускает процесс загрузки `CBindStatusCallback` объекте и вызывает метод `StartAsyncDownload`.|
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Вызывается асинхронный моникер для получения сведений о типа привязки должен быть создан.|
|[CBindStatusCallback::GetPriority](#getpriority)|Вызывается асинхронный моникер для получения приоритета операции привязки. Возвращает реализацию ATL `E_NOTIMPL`.|
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Вызывается, чтобы предоставлять данные для приложения, так как она станет доступной. Считывает данные, а затем вызывает функцию, передаваемую в его для использования данных.|
|[CBindStatusCallback::OnLowResource](#onlowresource)|Вызывается, когда не хватает ресурсов. Реализация ATL, возвращается значение s_ок.|
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Вызывается асинхронный моникер для передачи указателя на интерфейс объекта приложения. Реализация ATL, возвращается значение s_ок.|
|[CBindStatusCallback::OnProgress](#onprogress)|Вызывается для указания хода выполнения процесса скачивания данных. Реализация ATL, возвращается значение s_ок.|
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Вызывается при запуске привязки.|
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Вызывается, когда асинхронная передача данных остановлена.|
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|Инициализирует доступных байтов и байтов, считанных в нуль, создает объект потока нажимную из URL-адрес и вызывает `OnDataAvailable` каждый раз данные недоступны.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Число байтов, доступных для чтения.|
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Общее число считанных байтов.|
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Указатель на функцию вызывается, когда данные недоступны.|
|[CBindStatusCallback::m_pT](#m_pt)|Указатель на объекте, запрашивающем асинхронная передача данных.|
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Указатель на [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) интерфейс для текущей операции привязки.|
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Указатель на `IBinding` интерфейс для текущей операции привязки.|
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Указатель на [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) интерфейс для URL-адрес для использования.|
|[CBindStatusCallback::m_spStream](#m_spstream)|Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейс для передачи данных.|

## <a name="remarks"></a>Примечания

Класс `CBindStatusCallback` реализует интерфейс `IBindStatusCallback`. `IBindStatusCallback` должен быть реализован в приложении, что она позволяет получать уведомления из асинхронная передача данных. Использует асинхронный моникер, предоставляемые системой `IBindStatusCallback` методы для отправки и получения сведения об асинхронных данных передачу объекта.

Как правило `CBindStatusCallback` связывается с операции определенной привязки. Например, в [ASYNC](../../visual-cpp-samples.md) пример, при установке свойства URL-адрес, он создает `CBindStatusCallback` объекта в вызове `Download`:

[!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]

Функция обратного вызова используется асинхронный моникер `OnData` для вызова приложения, когда в нем данных. Асинхронный моникер предоставляемого системой.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CComObjectRootBase`

`IBindStatusCallback`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`CBindStatusCallback`

## <a name="requirements"></a>Требования

**Заголовок:** atlctl.h

##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback

Конструктор.

```
CBindStatusCallback();
```

### <a name="remarks"></a>Примечания

Создает объект для получения уведомлений, касающиеся асинхронная передача данных. Как правило один объект создается для каждой операции привязки.

Конструктор также инициализирует [m_pT](#m_pt) и [m_pFunc](#m_pfunc) значение NULL.

##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback

Деструктор

```
~CBindStatusCallback();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="download"></a>  CBindStatusCallback::Download

Создает `CBindStatusCallback` и вызывает `StartAsyncDownload` запустить асинхронную загрузку данных из указанного URL-адреса.

```
static HRESULT Download(
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```

### <a name="parameters"></a>Параметры

*pT*<br/>
[in] Указатель на объекте, запрашивающем асинхронная передача данных. `CBindStatusCallback` Шаблонизируется в объект класса этого объекта.

*pFunc*<br/>
[in] Указатель на функцию, которая получает данные, доступен для чтения. Функция является членом класса объекта типа `T`. См. в разделе [StartAsyncDownload](#startasyncdownload) синтаксис и примеры.

*bstrURL*<br/>
[in] Для получения данных из URL-адрес. Может быть любой допустимый URL-адрес или имя файла. Не может принимать значение NULL. Пример:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] `IUnknown` Контейнера. Значение NULL по умолчанию.

*bRelative*<br/>
[in] Флаг, указывающий, является ли URL-адрес является относительным или абсолютным. Значение FALSE по умолчанию, то есть URL-адрес является абсолютным.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Каждый раз, данные недоступны отправкой к объекту, используя `OnDataAvailable`. `OnDataAvailable` Считывает данные и вызывает функцию, на которые указывают *pFunc* (например, для хранения данных или печатать его на экран).

##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo

Вызывается, чтобы определить способ привязки моникера.

```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```

### <a name="parameters"></a>Параметры

*pgrfBSCF*<br/>
[out] Указатель на значения перечисления BINDF, указывающее, как должно выполняться операции привязки. По умолчанию значение с помощью следующих значений перечисления:

BINDF_ASYNCHRONOUS асинхронной загрузки.

BINDF_ASYNCSTORAGE `OnDataAvailable` возвращает E_PENDING в том случае, если данные еще не доступны вместо блокировки, пока данные недоступны.

BINDF_GETNEWESTVERSION операция привязки должна получить последнюю версию данных.

BINDF_NOWRITECACHE, операция привязки не следует хранить полученные данные в дисковом кэше.

*pbindinfo*<br/>
[in, out] Указатель на `BINDINFO` структуры, предоставляя дополнительные сведения о том, как объект намеревается привязки.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Реализация по умолчанию задает привязку выполняться асинхронно и использовать модель передачи данных. В модели принудительной отправки данных моникер управляет операция асинхронной привязки и постоянно уведомляет клиента, когда новые данные будут доступны.

##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority

Вызывается асинхронный моникер для получения приоритета операции привязки.

```
STDMETHOD(GetPriority)(LONG* pnPriority);
```

### <a name="parameters"></a>Параметры

*pnPriority*<br/>
[out] Адрес **LONG** переменную, которая, в случае успешного выполнения получает приоритет.

### <a name="return-value"></a>Возвращаемое значение

Возвращает E_NOTIMPL.

##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead

Можно использовать для хранения числа байтов, доступных для чтения.

```
DWORD m_dwAvailableToRead;
```

### <a name="remarks"></a>Примечания

Инициализированный к нулю `StartAsyncDownload`.

##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead

Общее количество байтов, считанных в асинхронную передачу данных.

```
DWORD m_dwTotalRead;
```

### <a name="remarks"></a>Примечания

Значение счетчика увеличивается каждый раз `OnDataAvailable` вызывается на число фактически считанных байтов. Инициализированный к нулю `StartAsyncDownload`.

##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc

Функция, на которые указывают `m_pFunc` вызывается `OnDataAvailable` после считывания доступных данных (например, для хранения данных или печатать его на экран).

```
ATL_PDATAAVAILABLE m_pFunc;
```

### <a name="remarks"></a>Примечания

Функция, на которые указывают `m_pFunc` является членом класса объекта и имеет следующий синтаксис:

```
void Function_Name(
   CBindStatusCallback<T>* pbsc,
   BYTE* pBytes,
   DWORD dwSize
   );
```

##  <a name="m_pt"></a>  CBindStatusCallback::m_pT

Указатель на объекте, запрашивающем асинхронная передача данных.

```
T* m_pT;
```

### <a name="remarks"></a>Примечания

`CBindStatusCallback` Шаблонизируется в объект класса этого объекта.

##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx

Указатель на [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) интерфейс, который предоставляет доступ к контексту привязки (объект, который хранит сведения об операциях привязки к конкретной моникер).

```
CComPtr<IBindCtx> m_spBindCtx;
```

### <a name="remarks"></a>Примечания

Инициализируется в `StartAsyncDownload`.

##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding

Указатель на `IBinding` интерфейс текущей операции привязки.

```
CComPtr<IBinding> m_spBinding;
```

### <a name="remarks"></a>Примечания

Инициализируется в `OnStartBinding` и выпущенном в `OnStopBinding`.

##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker

Указатель на [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) интерфейс для URL-адрес для использования.

```
CComPtr<IMoniker> m_spMoniker;
```

### <a name="remarks"></a>Примечания

Инициализируется в `StartAsyncDownload`.

##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream

Указатель на [IStream](/windows/desktop/api/objidl/nn-objidl-istream) интерфейс текущей операции привязки.

```
CComPtr<IStream> m_spStream;
```

### <a name="remarks"></a>Примечания

Инициализируется в `OnDataAvailable` из `STGMEDIUM` структуры при флаг BCSF BCSF_FIRSTDATANOTIFICATION и снимаются, когда флаг BCSF является BCSF_LASTDATANOTIFICATION.

##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable

Вызовы асинхронных моникеров, предоставляемых системой `OnDataAvailable` предоставлять данные для объекта, так как она станет доступной.

```
STDMETHOD(
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```

### <a name="parameters"></a>Параметры

*grfBSCF*<br/>
[in] Значение перечисления BSCF. Один или несколько из следующих: BSCF_FIRSTDATANOTIFICATION, BSCF_INTERMEDIARYDATANOTIFICATION или BSCF_LASTDATANOTIFICATION.

*dwSize*<br/>
[in] Совокупное объем (в байтах) данных, доступных с начала выполнения привязки. Может быть 0, указывающее, что объем данных, не соответствующие или стала доступной, не определенный срок.

*pFormatEtc*<br/>
[in] Указатель на [FORMATETC](/windows/desktop/com/the-formatetc-structure) структуру, содержащую формат доступных данных. Если формат не существует, может быть CF_NULL.

*pstgmed*<br/>
[in] Указатель на [STGMEDIUM](/windows/desktop/com/the-stgmedium-structure) структура, которая содержит фактические данные теперь доступна.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

`OnDataAvailable` Считывает данные, а затем вызывает метод класса объекта (например, для хранения данных или печатать его на экран). См. в разделе [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) сведения.

##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource

Вызывается, когда не хватает ресурсов.

```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable

Вызывается асинхронный моникер для передачи указателя на интерфейс объекта приложения.

```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор запрошенного интерфейса. Не используется.

*pUnk*<br/>
Адрес интерфейса IUnknown. Не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress

Вызывается для указания хода выполнения процесса скачивания данных.

```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```

### <a name="parameters"></a>Параметры

*ulProgress*<br/>
Длинное целое без знака. Не используется.

*ulProgressMax*<br/>
Длинное целое без знака не используется.

*ulStatusCode*<br/>
Длинное целое без знака. Не используется.

*szStatusText*<br/>
Адрес строковое значение. Не используется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK.

##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding

Задает элемент данных [m_spBinding](#m_spbinding) для `IBinding` указатель в *pBinding*.

```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```

### <a name="parameters"></a>Параметры

*dwReserved*<br/>
Зарезервировано для будущего использования.

*pBinding*<br/>
[in] Операция привязки адрес интерфейса IBinding текущего. Это не может быть NULL. Клиент должен вызвать метод AddRef на этот указатель, чтобы хранить ссылку на объект привязки.

##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding

Выпуски `IBinding` указатель в элементе данных [m_spBinding](#m_spbinding).

```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```

### <a name="parameters"></a>Параметры

*значение HRESULT*<br/>
Код состояния, возвращенный из операции привязки.

*szError*<br/>
Адрес строковое значение. Не используется.

### <a name="remarks"></a>Примечания

Вызывается средой асинхронных моникеров, предоставляемых системой для указания на конец операции привязки.

##  <a name="startasyncdownload"></a>  CBindStatusCallback::StartAsyncDownload

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

*pT*<br/>
[in] Указатель на объекте, запрашивающем асинхронная передача данных. `CBindStatusCallback` Шаблонизируется в объект класса этого объекта.

*pFunc*<br/>
[in] Указатель на функцию, которая получает считываемых данных. Функция является членом класса объекта типа `T`. См. в разделе **"Примечания"** синтаксис и примеры.

*bstrURL*<br/>
[in] Для получения данных из URL-адрес. Может быть любой допустимый URL-адрес или имя файла. Не может принимать значение NULL. Пример:

`CComBSTR mybstr =_T("http://somesite/data.htm")`

*pUnkContainer*<br/>
[in] `IUnknown` Контейнера. Значение NULL по умолчанию.

*bRelative*<br/>
[in] Флаг, указывающий, является ли URL-адрес является относительным или абсолютным. Значение FALSE по умолчанию, то есть URL-адрес является абсолютным.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Каждый раз, данные недоступны отправкой к объекту, используя `OnDataAvailable`. `OnDataAvailable` Считывает данные и вызывает функцию, на которые указывают *pFunc* (например, для хранения данных или печатать его на экран).

Функция, на которые указывают *pFunc* является членом класса объекта и имеет следующий синтаксис:

```
void Function_Name(
    CBindStatusCallback<T>* pbsc,
    BYTE* pBytes,
    DWORD dwSize);
```

В следующем примере (из [ASYNC](../../visual-cpp-samples.md) пример), функция `OnData` записывает полученные данные в текстовом поле.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
