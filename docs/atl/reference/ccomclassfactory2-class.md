---
title: Класс CComClassFactory2 | Документация Майкрософт
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
ms.openlocfilehash: 42ee8ab5fe6e410cf812c7c147f4673803b81903
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880194"
---
# <a name="ccomclassfactory2-class"></a>Класс CComClassFactory2
Этот класс реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс.  
  
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
  
- **статические VerifyLicenseKey BOOL (BSTR** `bstr` **);**  
  
- **статические GetLicenseKey BOOL (DWORD** `dwReserved` **, BSTR\***  `pBstr` **);**  
  
- **статические BOOL IsLicenseValid ();**  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComClassFactory2::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|  
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Лицензионный ключ создает объект с заданным идентификатором CLSID.|  
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Извлекает сведения, описывающие возможности лицензирования фабрики класса.|  
|[CComClassFactory2::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|  
|[CComClassFactory2::RequestLicKey](#requestlickey)|Создает и возвращает лицензионный ключ.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactory2` реализует [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720) интерфейс, который представляет собой расширение из [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364). `IClassFactory2` Создание элементов управления объекта через лицензию. Класс фабрики выполнение лицензированного компьютера можно предоставить ключ лицензии времени выполнения. Этот ключ лицензии позволяет приложению создавать экземпляры объектов, если лицензия весь компьютер не существует.  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрики класса по умолчанию. Чтобы использовать `CComClassFactory2`, укажите [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]  
  
 `CMyLicense`, для параметра-шаблона `CComClassFactory2`, необходимо реализовать статические функции `VerifyLicenseKey`, `GetLicenseKey`, и `IsLicenseValid`. Ниже приведен пример класса простой лицензии:  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]  
  
 `CComClassFactory2` наследует от `CComClassFactory2Base` и *лицензии*. `CComClassFactory2Base`, в свою очередь, является производным от `IClassFactory2` и `CComObjectRootEx< CComGlobalsThreadModel >`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 `license`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory2`  
  
 `CComClassFactory2`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory2::CreateInstance  
 Создает объект для указанного идентификатора CLSID и получает указатель интерфейса на этот объект.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkOuter*  
 [in] Если объект создается как часть агрегата, затем *pUnkOuter* должен быть внешняя Неизвестная строка. В противном случае *pUnkOuter* должен иметь значение NULL.  
  
 *riid*  
 [in] Идентификатор IID запрошенного интерфейса. Если *pUnkOuter* отлично от NULL, *riid* должно быть `IID_IUnknown`.  
  
 *ppvObj*  
 [out] Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppvObj* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Необходимо полностью лицензировать компьютера. Если лицензия весь компьютер не существует, вызов [CreateInstanceLic](#createinstancelic).  
  
##  <a name="createinstancelic"></a>  CComClassFactory2::CreateInstanceLic  
 Аналогичную [CreateInstance](#createinstance), за исключением того, что `CreateInstanceLic` требуется лицензионный ключ.  
  
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
 *pUnkOuter*  
 [in] Если объект создается как часть агрегата, затем *pUnkOuter* должен быть внешняя Неизвестная строка. В противном случае *pUnkOuter* должен иметь значение NULL.  
  
 *pUnkReserved*  
 [in] Не используется. Должен иметь значение NULL.  
  
 *riid*  
 [in] Идентификатор IID запрошенного интерфейса. Если *pUnkOuter* отлично от NULL, *riid* должно быть `IID_IUnknown`.  
  
 *bstrKey*  
 [in] Во время выполнения лицензионный ключ, ранее полученный из вызова `RequestLicKey`. Этот ключ необходим для создания объекта.  
  
 *ppvObject*  
 [out] Указатель на указатель интерфейса, заданный параметром *riid*. Если объект не поддерживает этот интерфейс *ppvObject* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Вы можете получить ключа лицензии с помощью [RequestLicKey](#requestlickey). Чтобы создать объект на машине без лицензии, необходимо вызвать `CreateInstanceLic`.  
  
##  <a name="getlicinfo"></a>  CComClassFactory2::GetLicInfo  
 Заполняет [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структуры со сведениями, описывающими фабрики класса рамках лицензионных возможности.  
  
```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```  
  
### <a name="parameters"></a>Параметры  
 *pLicInfo*  
 [out] Указатель на `LICINFO` структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `fRuntimeKeyAvail` Член этой структуры указывает, учитывая лицензионный ключ, фабрика классов разрешает ли создавать на машине нелицензированного объекты. *FLicVerified* элемент указывает, существует ли лицензия весь компьютер.  
  
##  <a name="lockserver"></a>  CComClassFactory2::LockServer  
 Увеличивает и уменьшает счетчик блокировки модуля путем вызова `_Module::Lock` и `_Module::Unlock`, соответственно.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>Параметры  
 *fLock*  
 [in] Если значение равно TRUE, увеличивается счетчик блокировок; в противном случае уменьшается количество блокировок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 `_Module` ссылается на глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
 Вызов `LockServer` позволяет клиенту, чтоб фабрику класса для создания нескольких объектов можно быстро.  
  
##  <a name="requestlickey"></a>  CComClassFactory2::RequestLicKey  
 Создает и возвращает лицензионный ключ, при условии, что `fRuntimeKeyAvail` членом [LICINFO](http://msdn.microsoft.com/library/windows/desktop/ms690590) структура имеет значение TRUE.  
  
```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Параметры  
 *dwReserved*  
 [in] Не используется. Должен равняться нулю.  
  
 *pbstrKey*  
 [out] Указатель на лицензионный ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Лицензионный ключ необходим для вызова метода [CreateInstanceLic](#createinstancelic) для создания объекта на машине без лицензии. Если `fRuntimeKeyAvail` имеет значение FALSE, то объекты могут создаваться только на полностью лицензированную компьютере.  
  
 Вызовите [GetLicInfo](#getlicinfo) для извлечения значения `fRuntimeKeyAvail`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [Класс CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
