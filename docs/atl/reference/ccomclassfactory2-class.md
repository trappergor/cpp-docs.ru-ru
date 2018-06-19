---
title: Класс CComClassFactory2 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da2b47290d3d0be525ca65b16733c9f42835d24e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363520"
---
# <a name="ccomclassfactory2-class"></a>Класс CComClassFactory2
Этот класс реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class license>  
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```  
  
#### <a name="parameters"></a>Параметры  
 *Лицензии*  
 Класс, реализующий следующие статические функции:  
  
- **статические VerifyLicenseKey BOOL (BSTR** `bstr` **);**  
  
- **GetLicenseKey статические BOOL (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **статические BOOL IsLicenseValid ();**  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Лицензионный ключ создает объект для указанного идентификатора CLSID.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Получает сведения, описывающие возможности лицензирования фабрики класса.|  
|[CComClassFactory2::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Создает и возвращает лицензионный ключ.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactory2` реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс, который представляет собой расширение для [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** создавать с помощью лицензии объекта элементов управления. Выполнения фабрики класса лицензированных компьютера можно ввести ключ лицензии во время выполнения. Это лицензионный ключ позволяет приложению для создания экземпляров объектов, при полной машины лицензии не существует.  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, параметр шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простого лицензии:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` наследует от **CComClassFactory2Base** и *лицензии*. **CComClassFactory2Base**, в свою очередь, является производным от **IClassFactory2** и **CComObjectRootEx\< CComGlobalsThreadModel >**.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance  
 Создает объект для указанного идентификатора CLSID и возвращает указатель интерфейса на этот объект.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [in] Если объект создается как часть агрегата, затем `pUnkOuter` должен быть внешняя Неизвестная строка. В противном случае `pUnkOuter` должно быть **NULL**.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Если `pUnkOuter` не является **NULL**, `riid` должно быть **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Указатель на указатель на интерфейс, определяемый `riid`. Если объект не поддерживает этот интерфейс `ppvObj` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Необходимо иметь лицензию полностью компьютера. Если полного лицензия не существует, вызов [CreateInstanceLic](#createinstancelic).  
  
##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic  
 Аналогично [CreateInstance](#createinstance), за исключением того, что `CreateInstanceLic` требует лицензионный ключ.  
  
```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
 */,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [in] Если объект создается как часть агрегата, затем `pUnkOuter` должен быть внешняя Неизвестная строка. В противном случае `pUnkOuter` должно быть **NULL**.  
  
 *pUnkReserved*  
 [in] Не используется. Должно быть **NULL**.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Если `pUnkOuter` не является **NULL**, `riid` должно быть **IID_IUnknown**.  
  
 `bstrKey`  
 [in] Во время выполнения лицензионный ключ, ранее получены из вызова `RequestLicKey`. Этот ключ необходим для создания объекта.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, определяемое `riid`. Если объект не поддерживает этот интерфейс `ppvObject` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Вы можете получить ключа лицензии с помощью [RequestLicKey](#requestlickey). Чтобы создать объект на машине без лицензии, необходимо вызвать метод `CreateInstanceLic`.  
  
##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo  
 Заполняет [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структуру с информацию, описывающую класс фабрики лицензирования возможностей.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pLicInfo*  
 [out] Указатель на **LICINFO** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 `fRuntimeKeyAvail` Член этой структуры указывает ли, учитывая лицензионный ключ, фабрики класса позволяет создавать на машине нелицензионного объекты. *FLicVerified* элемент указывает, существует ли полного лицензию.  
  
##  <a name="lockserver"></a>  CComClassFactory2::LockServer  
 Увеличение и уменьшение, счетчик блокировок модуля путем вызова **_Module::Lock** и **_Module::Unlock**соответственно.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Параметры  
 `fLock`  
 [in] Если **TRUE**, счетчик блокировок увеличивается; в противном случае, уменьшается на единицу счетчик блокировок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 **_Module** ссылается на глобальный экземпляр класса [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
 Вызов `LockServer` позволяет клиенту удерживаться в фабрику класса, чтобы быстро создать несколько объектов.  
  
##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey  
 Создает и возвращает лицензионный ключ, при условии, что `fRuntimeKeyAvail` членом [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структура **TRUE**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 [in] Не используется. Должен равняться нулю.  
  
 `pbstrKey`  
 [out] Указатель на ключ лицензии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Лицензионный ключ является обязательным для вызова [CreateInstanceLic](#createinstancelic) для создания объекта на компьютере без лицензии. Если `fRuntimeKeyAvail` — **FALSE**, а затем объекты могут создаваться только на компьютере, полностью лицензированной.  
  
 Вызовите [GetLicInfo](#getlicinfo) для извлечения значения `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [Класс CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
