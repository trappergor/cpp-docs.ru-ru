---
title: Класс CComCachedTearOffObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1072faed01033bec9fec127318334f8a61ac29e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
 Перемещаемые класс, производный от `CComTearOffObjectBase` и интерфейсы нужно объекта перемещаемые для поддержки.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|Конструктор.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|Увеличивает счетчик ссылок для `CComCachedTearOffObject` объекта.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|Вызовы `m_contained::FinalConstruct` (перемещаемые метода класса).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|Вызовы `m_contained::FinalRelease` (перемещаемые метода класса).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на `IUnknown` из `CComCachedTearOffObject` объекта, или на запрошенный интерфейс для класса перемещаемые (класс `contained`).|  
|[CComCachedTearOffObject::Release](#release)|Уменьшает счетчик ссылок для `CComCachedTearOffObject` объекта и удаляет его, если счетчик ссылок равен 0.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|Объект `CComContainedObject` объект, производный от класса перемещаемые (класс `contained`).|  
  
## <a name="remarks"></a>Примечания  
 `CComCachedTearOffObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) перемещаемые интерфейса. Этот класс отличается от `CComTearOffObject` в том, что `CComCachedTearOffObject` имеет свой собственный **IUnknown**, отдельно от владельца объекта **IUnknown** (владельца — объект, для которого перемещаемое создается). `CComCachedTearOffObject` сохраняет свой собственный количество ссылок на его **IUnknown** и удаляет себя, когда его счетчик ссылок равен нулю. Тем не менее, при выполнении запроса для любого из его перемещаемые интерфейсы, количество ссылок на объект-владелец **IUnknown** увеличивается.  
  
 Если `CComCachedTearOffObject` объектов реализации перемещаемое уже создан и еще раз, то запрашивается интерфейс перемещаемые `CComCachedTearOffObject` объект повторно. Напротив, если реализация интерфейса перемещаемые `CComTearOffObject` снова запрашиваются через объект-владелец другой `CComTearOffObject` будет создан.  
  
 Владелец класс должен реализовывать `FinalRelease` и вызовите **выпуска** на кэшированные **IUnknown** для `CComCachedTearOffObject`, который уменьшит счетчик ссылок. Это приведет к `CComCachedTearOffObject` `FinalRelease` вызываться и удалить перемещаемое.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>  CComCachedTearOffObject::AddRef  
 Увеличивает число ссылок `CComCachedTearOffObject` объекта на 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomcachedtearoffobject"></a>  CComCachedTearOffObject::CComCachedTearOffObject  
 Конструктор.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Указатель на **IUnknown** из `CComCachedTearOffObject`.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComContainedObject` член, [m_contained](#m_contained).  
  
##  <a name="dtor"></a>  CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 Деструктор  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает метод [FinalRelease](#finalrelease).  
  
##  <a name="finalconstruct"></a>  CComCachedTearOffObject::FinalConstruct  
 Вызовы **m_contained::FinalConstruct** для создания `m_contained`, `CComContainedObject` <  `contained`> объект, используемый для доступа к интерфейс, реализованный класс перемещаемые.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="finalrelease"></a>  CComCachedTearOffObject::FinalRelease  
 Вызовы **m_contained::FinalRelease** для освобождения `m_contained`, `CComContainedObject` <  `contained`> объекта.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComCachedTearOffObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от класса перемещаемые.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>Параметры  
 `contained`  
 [in] Перемещаемые класс, производный от `CComTearOffObjectBase` и интерфейсы нужно объекта перемещаемые для поддержки.  
  
### <a name="remarks"></a>Примечания  
 Методы `m_contained` наследует используются для доступа к перемещаемые интерфейса в классе перемещаемые через кэшированных перемещаемые объекта `QueryInterface`, `FinalConstruct`, и `FinalRelease`.  
  
##  <a name="queryinterface"></a>  CComCachedTearOffObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель на интерфейс, определяемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если запрошенный интерфейс **IUnknown**, возвращает указатель на `CComCachedTearOffObject`в собственной **IUnknown** и увеличивает счетчик ссылок. В противном случае запрашивает интерфейс класса перемещаемые при помощи [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) метод наследуется от `CComObjectRootEx`.  

  
##  <a name="release"></a>  CComCachedTearOffObject::Release  
 Уменьшает число ссылок на 1 и, если счетчик ссылок равен 0, удаляет `CComCachedTearOffObject` объекта.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В неотладочных сборках всегда возвращает 0. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
## <a name="see-also"></a>См. также  
 [Класс CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
