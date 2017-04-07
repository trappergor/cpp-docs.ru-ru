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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: a0c1c115bfffa1de9a2a8c91c5268de66c68e7cd
ms.lasthandoff: 03/31/2017

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
|[CComClassFactory::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactory`реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейс, который содержит методы для создания объекта конкретного CLSID, а также блокировки фабрики класса в памяти и позволяют быстрее создавать новые объекты. **IClassFactory** должен быть реализован для каждого класса, зарегистрированный в системном реестре и которые присваивают CLSID.  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Чтобы переопределить это поведение по умолчанию, укажите один из `DECLARE_CLASSFACTORY` *XXX* макросы в определении класса. Например [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) макрос использует указанный класс фабрики класса:  
  
 [!code-cpp[NVC_ATL_COM #8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 Указывает, что выше определения класса **CMyClassFactory** будет использоваться в качестве объекта фабрики класса по умолчанию. **CMyClassFactory** должен быть производным от `CComClassFactory` и Переопределите `CreateInstance`.  
  
 Библиотека ATL предоставляет три макроса, которые объявлять фабрики класса:  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) использует [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), какие элементы управления создавать с помощью лицензии.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) использует [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), который создает объекты в нескольких подразделениях.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) использует [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), который создает один [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactory::CreateInstance  
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
  
##  <a name="lockserver"></a>CComClassFactory::LockServer  
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
  
 Вызов `LockServer` позволяет клиенту удерживаться в фабрику класса, чтобы несколько объектов можно быстро создавать.  
  
## <a name="see-also"></a>См. также  
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

