---
title: "Класс CComClassFactorySingleton | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComClassFactorySingleton
- ATL.CComClassFactorySingleton<T>
- ATL::CComClassFactorySingleton
- ATL::CComClassFactorySingleton<T>
- CComClassFactorySingleton
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
caps.latest.revision: 21
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
ms.openlocfilehash: 7ff6f3a9d00c0f579077d9502aefad5cbea35f17
ms.lasthandoff: 02/24/2017

---
# <a name="ccomclassfactorysingleton-class"></a>Класс CComClassFactorySingleton
Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс.  
  
 `CComClassFactorySingleton`является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта. Каждый вызов `CreateInstance` метод просто запрашивает этот объект для указателя на интерфейс.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Запросы `m_spObj` для указателя на интерфейс.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) создаваемый объект `CComClassFactorySingleton`.|  
  
## <a name="remarks"></a>Примечания  
 Объекты ATL обычно получения фабрики класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4), который объявляет `CComClassFactory` как фабрика класса по умолчанию. Для использования `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](http://msdn.microsoft.com/library/0e4a3964-c03d-463e-884c-fe3b416db478) макрос в определении класса объекта. Например:  
  
 [!code-cpp[NVC_ATL_COM&#10;](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-namecreateinstancea--ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a>CComClassFactorySingleton::CreateInstance  
 Вызовы `QueryInterface` через [m_spObj](#m_spobj) для получения указателя интерфейса.  
  
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
  
##  <a name="a-namemspobja--ccomclassfactorysingletonmspobj"></a><a name="m_spobj"></a>CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) создаваемый объект `CComClassFactorySingleton`.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>Примечания  
 Каждый вызов [CreateInstance](#createinstance) метод просто запрашивает этот объект для указателя на интерфейс.  
  
 Обратите внимание, что текущую форму `m_spObj` представляется критических изменений из-за способа, `CComClassFactorySingleton` работали в предыдущих версиях библиотеки ATL. В предыдущих версиях `CComClassFactorySingleton` объект был создан в то же время, как фабрика класса при инициализации сервера. В Visual C++ .NET 2003 объект создается неактивно, при первом запросе. Это изменение может вызвать ошибки в программах, которые полагаются на раннюю инициализацию.  
  
## <a name="see-also"></a>См. также  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)   
 [Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

