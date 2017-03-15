---
title: "Класс CComCachedTearOffObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComCachedTearOffObject
- ATL.CComCachedTearOffObject
- ATL.CComCachedTearOffObject<contained>
- CComCachedTearOffObject
- ATL::CComCachedTearOffObject<contained>
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 96f040c732c5545a9b8febb32fcb1636f0fe4a40
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcachedtearoffobject-class"></a>Класс CComCachedTearOffObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) перемещаемые интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Параметры  
 `contained`  
 Перемещаемое класс, производный от `CComTearOffObjectBase` и интерфейсы требуется объект перемещаемые для поддержки.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Конструктор.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|Увеличивает значение счетчика ссылок для `CComCachedTearOffObject` объекта.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Вызовы `m_contained::FinalConstruct` (перемещаемые метода класса).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Вызовы `m_contained::FinalRelease` (перемещаемые метода класса).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на `IUnknown` из `CComCachedTearOffObject` объекта, или на запрошенный интерфейс в классе перемещаемые (класс `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Уменьшает счетчик ссылок для `CComCachedTearOffObject` объекта и удаляет его, если счетчик ссылок равен 0.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|Объект `CComContainedObject` объект, производный от класса перемещаемые (класс `contained`).|  
  
## <a name="remarks"></a>Примечания  
 `CComCachedTearOffObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) перемещаемые интерфейса. Этот класс отличается от `CComTearOffObject` , `CComCachedTearOffObject` имеет свой собственный **IUnknown**, отдельно от владельца объекта **IUnknown** (владелец является объектом, для которого перемещаемое создается). `CComCachedTearOffObject`использует свой собственный счетчика ссылок на его **IUnknown** и удаляет себя, когда его счетчик ссылок равен нулю. Тем не менее, если запрос для любого из его перемещаемые интерфейсы, счетчик ссылок объекта владельца **IUnknown** увеличивается.  
  
 Если `CComCachedTearOffObject` объекта реализации перемещаемое уже создан и еще раз, то запрашивается интерфейс перемещаемые `CComCachedTearOffObject` объект повторно. Напротив, если перемещаемое интерфейс реализован `CComTearOffObject` снова запрашиваются через объект владельца другой `CComTearOffObject` будет создан.  
  
 Владелец класс должен реализовывать `FinalRelease` и вызвать **выпуска** на кэшированный **IUnknown** для `CComCachedTearOffObject`, что уменьшит счетчик ссылок. Это приведет к `CComCachedTearOffObject`в `FinalRelease` вызываться и удалять перемещаемые.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameaddrefa--ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOffObject::AddRef  
 Увеличивает счетчик ссылок `CComCachedTearOffObject` объекта на 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="a-nameccomcachedtearoffobjecta--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 Конструктор.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Указатель на **IUnknown** из `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComContainedObject` член, [m_contained](#m_contained).  
  
##  <a name="a-namedtora--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 Деструктор  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает [FinalRelease](#finalrelease).  
  
##  <a name="a-namefinalconstructa--ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 Вызовы **m_contained::FinalConstruct** для создания `m_contained`, `CComContainedObject` <  `contained`настроек объект, используемый для доступа к интерфейсу, реализуемый класс перемещаемые.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="a-namefinalreleasea--ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 Вызовы **m_contained::FinalRelease** для освобождения `m_contained`, `CComContainedObject` <  `contained`настроек объекта.  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomcachedtearoffobjectmcontained"></a><a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от класса перемещаемые.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Параметры  
 `contained`  
 [in] Перемещаемое класс, производный от `CComTearOffObjectBase` и интерфейсы требуется объект перемещаемые для поддержки.  
  
### <a name="remarks"></a>Примечания  
 Методы `m_contained` наследует используются для доступа к перемещаемые интерфейс в классе перемещаемые через кэшированных перемещаемые объекта `QueryInterface`, `FinalConstruct`, и `FinalRelease`.  
  
##  <a name="a-namequeryinterfacea--ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если запрошенный интерфейс **IUnknown**, возвращает указатель на `CComCachedTearOffObject`в собственной **IUnknown** и увеличивает значение счетчика ссылок. В противном случае — запрашивает интерфейс класса перемещаемые с помощью [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) метод наследуется от `CComObjectRootEx`.  

  
##  <a name="a-namereleasea--ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOffObject::Release  
 Уменьшает число ссылок на 1 и, если счетчик ссылок равен 0, удаляет `CComCachedTearOffObject` объекта.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В сборках неотладочные всегда возвращает значение 0. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
## <a name="see-also"></a>См. также  
 [Класс CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

