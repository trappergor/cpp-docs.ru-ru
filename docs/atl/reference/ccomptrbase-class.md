---
title: Класс CComPtrBase | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea90c1394da9b6a202b121a0e521f99acaba8264
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomptrbase-class"></a>Класс CComPtrBase
Этот класс предоставляет основу для классов интеллектуальных указателей, использование памяти на основе COM процедур.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CComPtrBase
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, на которые ссылается интеллектуального указателя.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtrBase::Advise](#advise)|Этот метод вызывается для создания подключения `CComPtrBase`точки подключения и приемником клиента.|  
|[CComPtrBase::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|Этот метод вызывается для создания объекта класса, связанного с указанным Идентификатором класса или идентификатор программы.|  
|[CComPtrBase::CopyTo](#copyto)|Этот метод вызывается для копирования `CComPtrBase` указатель на другую переменную указателя.|  
|[CComPtrBase::Detach](#detach)|Вызовите этот метод для освобождения владения указателя.|  
|[CComPtrBase::IsEqualObject](#isequalobject)|Вызовите этот метод для проверки, если указанный **IUnknown** указывает на тот же объект, связанный с `CComPtrBase` объекта.|  
|[CComPtrBase::QueryInterface](#queryinterface)|Этот метод используется для возврата указателя для указанного интерфейса.|  
|[CComPtrBase::Release](#release)|Вызовите этот метод для освобождения интерфейс.|  
|[CComPtrBase::SetSite](#setsite)|Вызовите этот метод, чтобы задать для сайта `CComPtrBase` объект **IUnknown** родительского объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtrBase::operator T *](#operator_t_star)|Оператор приведения.|  
|[CComPtrBase::operator!](#operator_not)|Оператор NOT.|  
|[CComPtrBase::operator &](#operator_amp)|& Оператор.|  
|[CComPtrBase::operator *](#operator_star)|* Оператор.|  
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|Меньше-оператор.|  
|[CComPtrBase::operator ==](#operator_eq_eq)|Оператор равенства.|  
|[CComPtrBase::operator ->](#operator_ptr)|Оператор члены указателя.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtrBase::p](#p)|Переменная члена данных указателя.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс служит основой для других интеллектуальные указатели, которые используют процедур управления памятью COM, такие как [CComQIPtr](../../atl/reference/ccomqiptr-class.md) и [CComPtr](../../atl/reference/ccomptr-class.md). Производные классы добавлять свои собственные конструкторы и операторы, но полагаться на методы, предоставляемые классом `CComPtrBase`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="advise"></a>  CComPtrBase::Advise  
 Этот метод вызывается для создания подключения `CComPtrBase`точки подключения и приемником клиента.  
  
```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 Указатель на клиент **IUnknown**.  
  
 `iid`  
 Идентификатор GUID точки подключения. Как правило это то же самое исходящего интерфейса, управляемого с помощью точки подключения.  
  
 `pdw`  
 Указатель на файл cookie, однозначно определяющее соединение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 В разделе [AtlAdvise](connection-point-global-functions.md#atladvise) для получения дополнительной информации.  
  
##  <a name="attach"></a>  CComPtrBase::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* p2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p2`  
 `CComPtrBase` Объекта будет распоряжаться этот указатель.  
  
### <a name="remarks"></a>Примечания  
 **Присоединение** вызовы [CComPtrBase::Release](#release) в существующем [CComPtrBase::p](#p) переменной-члена, а затем назначает `p2` для `CComPtrBase::p`. Когда `CComPtrBase` принимает право на владение указатель, он будет автоматически вызывать `Release` на указатель, который будет удалить указатель и все выделенные данные, число ссылок на объект становится равным 0.  
  
##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase  
 Деструктор  
  
```
~CComPtrBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает интерфейс, который указывает `CComPtrBase`.  
  
##  <a name="cocreateinstance"></a>  CComPtrBase::CoCreateInstance  
 Этот метод вызывается для создания объекта класса, связанного с указанным Идентификатором класса или идентификатор программы.  
  
```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szProgID`  
 Указатель на идентификатор ProgID, используемую для восстановления CLSID.  
  
 `pUnkOuter`  
 Если **NULL**, указывает, что объект не создается в ходе статистической обработки. Если не **NULL**, — это указатель на Агрегатный объект **IUnknown** интерфейса (Управление **IUnknown**).  
  
 `dwClsContext`  
 Контекст, в котором будет выполняться код, управляющий вновь созданный объект.  
  
 `rclsid`  
 Идентификатор CLSID, связанный с данными и код, который будет использоваться для создания объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING или E_NOINTERFACE при сбое. В разделе [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) и [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) описание этих ошибок.  
  
### <a name="remarks"></a>Примечания  
 При вызове в первой форме метода [CLSIDFromProgID](http://msdn.microsoft.com/library/windows/desktop/ms688386) используется для восстановления CLSID. Затем вызовите обе формы [CoCreateClassInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
 В отладочных построениях, произойдет ошибка утверждения, если [CComPtrBase::p](#p) не равно NULL.  
  
##  <a name="copyto"></a>  CComPtrBase::CopyTo  
 Этот метод вызывается для копирования `CComPtrBase` указатель на другую переменную указателя.  
  
```
HRESULT CopyTo(T** ppT) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *ppT*  
 Адрес переменной, которая получит `CComPtrBase` указателя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успеха, E_POINTER в случае неудачи возвращает значение S_OK.  
  
### <a name="remarks"></a>Примечания  
 Копирует `CComPtrBase` указатель *ppT*. Счетчик ссылок для [CComPtrBase::p](#p) увеличивается переменной-члена.  
  
 Ошибка HRESULT будет возвращено, если *ppT* равен NULL. В отладочных построениях, произойдет ошибка утверждения, если *ppT* равен NULL.  
  
##  <a name="detach"></a>  CComPtrBase::Detach  
 Вызовите этот метод для освобождения владения указателя.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указателем, задает [CComPtrBase::p](#p) переменной-члена данных значение NULL и возвращает копию указателя.  
  
##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject  
 Вызовите этот метод для проверки, если указанный **IUnknown** указывает на тот же объект, связанный с `CComPtrBase` объекта.  
  
```
bool IsEqualObject(IUnknown* pOther) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pOther`  
 **IUnknown \***  для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объекты одинаковые.  
  
##  <a name="operator_not"></a>  CComPtrBase::operator!  
 Оператор NOT.  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если `CComHeapPtr` указатель равен NULL, значение false в противном случае.  
  
##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;  
 & Оператор.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес объекта, на который указывает `CComPtrBase` объекта.  
  
##  <a name="operator_star"></a>  CComPtrBase::operator *  
 * Оператор.  
  
```
T& operator*() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CComPtrBase::p](#p); то есть, указатель на объект, упоминаемый в `CComPtrBase` объекта.  
  
 Если отладочные построения, будет возникать ошибка утверждения, если [CComPtrBase::p](#p) не равно NULL.  
  
##  <a name="operator_eq_eq"></a>  CComPtrBase::operator ==  
 Оператор равенства.  
  
```
bool operator== (T* pT) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 Указатель на объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если `CComPtrBase` и *pT* пункты тот же объект, значение false в противном случае.  
  
##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;  

 Оператор указателя на член.  
  
```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CComPtrBase::p](#p) переменной-члена данных.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор используется для вызова метода в классе, который указывает `CComPtrBase` объекта. В отладочных построениях, произойдет сбой утверждения, если `CComPtrBase` член данных указывает на значение NULL.  
  
##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;  
 Меньше-оператор.  
  
```
bool operator<(T* pT) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *pT*  
 Указатель на объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если указатель управляется текущий объект меньше, чем указатель, с которым выполняется сравнение.  
  
##  <a name="operator_t_star"></a>  CComPtrBase::operator T *  
 Оператор приведения.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает указатель на тип объекта данных, определенные в шаблоне класса.  
  
##  <a name="p"></a>  CComPtrBase::p  
 Переменная члена данных указателя.  
  
```
T* p;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface  
 Этот метод используется для возврата указателя для указанного интерфейса.  
  
```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `Q`  
 Тип объекта, указатель интерфейса является обязательным.  
  
 `pp`  
 Адрес выходной переменной, которая получает указатель на запрошенный интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK на успех или E_NOINTERFACE при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [IUnknown::QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 В отладочных построениях, произойдет ошибка утверждения, если *pp* не равно NULL.  
  
##  <a name="release"></a>  CComPtrBase::Release  
 Вызовите этот метод для освобождения интерфейс.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Интерфейс освобождается, и [CComPtrBase::p](#p) имеет значение NULL.  
  
##  <a name="setsite"></a>  CComPtrBase::SetSite  
 Вызовите этот метод, чтобы задать для сайта `CComPtrBase` объект **IUnknown** родительского объекта.  
  
```
HRESULT SetSite(IUnknown* punkParent) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `punkParent`  
 Указатель на **IUnknown** интерфейса родительского элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или ошибку HRESULT при сбое.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
