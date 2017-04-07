---
title: "Класс CComClassFactory | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7c488732d7b32248acaaa5c5c9c6a29404c3872
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactory-class"></a>Класс CComClassFactory
Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|  
|[CComClassFactory::LockServer](#lockserver)|Блокирует фабрики классов в памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactory`реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс, который содержит методы для создания объекта для определенного идентификатора CLSID, а также блокировки фабрики классов в память позволяет более быстро создавать новые объекты. **IClassFactory** должен быть реализован для каждого класса, регистрация в системном реестре и который назначить CLSID.  
  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите одно из `DECLARE_CLASSFACTORY` *XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](http://msdn.microsoft.com/library/4181ef00-0f30-4e19-b0ee-e7648062e926) макрос использует указанный класс фабрики класса:  
  
 [!code-cpp[NVC_ATL_COM №&8;](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 Указывает, что выше определения класса **CMyClassFactory** будет использоваться как фабрика класса объекта по умолчанию. **CMyClassFactory** должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.  
  
 Библиотека ATL предоставляет три другие макросы, объявляющие фабрики класса:  
  
- [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), который контролирует создание с помощью лицензии.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory::CreateInstance  
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
  
##  <a name="lockserver"></a>CComClassFactory::LockServer  
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
  
 Вызов `LockServer` позволяет клиенту удерживать фабрики классов для создания нескольких объектов можно быстро.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

