---
title: "Класс CComContainedObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
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
ms.openlocfilehash: 60958f328d78205c3432f35ed4e3e3c4b652ebfe
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontainedobject-class"></a>Класс CComContainedObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) делегируя владельца объекта **IUnknown**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Конструктор. Инициализирует элемент указатель владельца объекта `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Увеличивает значение счетчика ссылок на владельца объекта.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Возвращает владельца объекта `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Извлекает указатель на интерфейс, запрошенный в объекте владельца.|  
|[CComContainedObject::Release](#release)|Уменьшает счетчик ссылок на объект владельца.|  
  
## <a name="remarks"></a>Примечания  
 Использует ATL `CComContainedObject` в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), и [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) делегируя владельца объекта **IUnknown**. (Им является внешний объект статистической обработки или объект, для которого создается интерфейс перемещаемое.) `CComContainedObject` вызовов `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease`, наследуемых через `Base`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="addref"></a>CComContainedObject::AddRef  
 Увеличивает значение счетчика ссылок на владельца объекта.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 Конструктор.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Владельца объекта **IUnknown**.  
  
### <a name="remarks"></a>Примечания  
 Наборы `m_pOuterUnknown` указателя на член (унаследованные `Base` класса) для `pv`.  
  
##  <a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 Деструктор  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 Возвращает `m_pOuterUnknown` указателя на член (унаследованные *базы* класса), содержащий объект владельца **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Владельца объекта **IUnknown**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть виртуальными Если `Base` объявил [DECLARE_GET_CONTROLLING_UNKNOWN](http://msdn.microsoft.com/library/82b0199a-a9d5-4f95-a711-fa1ae18e1f77) макрос.  
  
##  <a name="queryinterface"></a>CComContainedObject::QueryInterface  
 Извлекает указатель на интерфейс, запрошенный в объекте владельца.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`. Если объект не поддерживает этот интерфейс `ppvObject` равен **NULL**.  
  
 `pp`  
 [out] Указатель на указатель интерфейса, определенный по типу `Q`. Если объект не поддерживает этот интерфейс `pp` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="release"></a>CComContainedObject::Release  
 Уменьшает счетчик ссылок на объект владельца.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В сборках неотладочные **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

