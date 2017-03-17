---
title: "Класс CComClassFactory2 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3787214d5479e1cd57295c9c25335e87651a16bb
ms.lasthandoff: 02/24/2017

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
 *лицензии*  
 Класс, реализующий следующие статические функции:  
  
- **VerifyLicenseKey статические BOOL (BSTR** `bstr` **);**  
  
- **GetLicenseKey статические BOOL (DWORD** `dwReserved` **, BSTR\* ** `pBstr` **);**  
  
- **статические (BOOL IsLicenseValid);**  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Создает объект для указанного идентификатора CLSID ключ лицензии.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Получает сведения, описывающие возможности лицензирования фабрики класса.|  
|[CComClassFactory2::LockServer](#lockserver)|Блокирует фабрики классов в памяти.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Создает и возвращает лицензионный ключ.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactory2`реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс, который представляет собой расширение для [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). **IClassFactory2** элементы управления объекта создание с помощью лицензии. Класс фабрики выполнение лицензированного компьютера можно предоставить ключ лицензии во время выполнения. Этот ключ лицензии позволяет приложению создавать экземпляры объектов, при полной машины лицензии не существует.  
  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) макрос в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 **CMyLicense**, параметр шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простые лицензии:  
  
 [!code-cpp[NVC_ATL_COM&#3;](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2`наследует от **CComClassFactory2Base** и *лицензий*. **CComClassFactory2Base**, в свою очередь, является производным от **IClassFactory2** и **CComObjectRootEx\< CComGlobalsThreadModel настроек**.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory2::CreateInstance  
 Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [in] Если объект создается в ходе статистической обработки, затем `pUnkOuter` должен быть внешнего неизвестен. В противном случае — `pUnkOuter` должно быть **NULL**.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Если `pUnkOuter` отличен от **NULL**, `riid` должно быть **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Указатель на указатель интерфейса, идентифицируемый `riid`. Если объект не поддерживает этот интерфейс `ppvObj` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Необходимо иметь лицензию полностью компьютера. Если лицензия полного не существует, вызов [CreateInstanceLic](#createinstancelic).  
  
##  <a name="createinstancelic"></a>CComClassFactory2::CreateInstanceLic  
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
 [in] Если объект создается в ходе статистической обработки, затем `pUnkOuter` должен быть внешнего неизвестен. В противном случае — `pUnkOuter` должно быть **NULL**.  
  
 *pUnkReserved*  
 [in] Не используется. Должно быть **NULL**.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Если `pUnkOuter` отличен от **NULL**, `riid` должно быть **IID_IUnknown**.  
  
 `bstrKey`  
 [in] Во время выполнения лицензионный ключ, ранее получены из вызова `RequestLicKey`. Этот ключ необходим для создания объекта.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, заданный по `riid`. Если объект не поддерживает этот интерфейс `ppvObject` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Вы можете получить лицензионного ключа использовать [RequestLicKey](#requestlickey). Чтобы создать объект на машине нелицензионных, необходимо вызвать метод `CreateInstanceLic`.  
  
##  <a name="getlicinfo"></a>CComClassFactory2::GetLicInfo  
 Заполняет [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структуры сведения, описывающие фабрика классов по лицензированию возможности.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pLicInfo*  
 [out] Указатель на **LICINFO** структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 `fRuntimeKeyAvail` Этой структуры указывает, учитывая лицензионный ключ, фабрика классов позволяет ли объекты для создания на машине нелицензионного. *FLicVerified* элемент указывает, существует ли полного лицензии.  
  
##  <a name="lockserver"></a>CComClassFactory2::LockServer  
 Увеличение и уменьшение счетчик блокировок модуля путем вызова **_Module::Lock** и **_Module::Unlock**соответственно.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Параметры  
 `fLock`  
 [in] Если **TRUE**число блокировок увеличивается; в противном случае, уменьшается на единицу счетчик блокировок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 **_Module** ссылается на глобальный экземпляр класса [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
 Вызов `LockServer` позволяет клиенту удерживать фабрики класса, чтобы быстро создать несколько объектов.  
  
##  <a name="requestlickey"></a>CComClassFactory2::RequestLicKey  
 Создает и возвращает лицензионный ключ, при условии, что `fRuntimeKeyAvail` членом [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структура **TRUE**.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 `dwReserved`  
 [in] Не используется. Должно быть нулем.  
  
 `pbstrKey`  
 [out] Указатель на ключ лицензии.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Лицензионный ключ является обязательным для вызова [CreateInstanceLic](#createinstancelic) для создания объекта на машине без лицензии. Если `fRuntimeKeyAvail` — **FALSE**, а затем объекты могут создаваться только на компьютере, полностью лицензированный.  
  
 Вызов [GetLicInfo](#getlicinfo) для извлечения значения `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [Класс CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

