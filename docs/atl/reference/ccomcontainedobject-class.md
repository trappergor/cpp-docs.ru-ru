---
title: "Класс CComContainedObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3579d4080b4dba130b58592fa47efd636805ed1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcontainedobject-class"></a>Класс CComContainedObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) делегирование для владельца объекта **IUnknown**.  
  
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Конструктор. Инициализирует член указатель на объект-владелец `IUnknown`.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|Увеличивает счетчик ссылок на объект-владелец.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Извлекает объект-владелец `IUnknown`.|  
|[CComContainedObject::QueryInterface](#queryinterface)|Извлекает указатель на интерфейс, запрошенный в объекте владельца.|  
|[CComContainedObject::Release](#release)|Уменьшает счетчик ссылок на объект-владелец.|  
  
## <a name="remarks"></a>Примечания  
 ATL использует `CComContainedObject` в классах [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), и [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) делегирование для владельца объекта **IUnknown**. (Им является внешний объект статистической обработки или объект, для которого создается интерфейсом перемещаемые.) `CComContainedObject` вызовы `CComObjectRootEx` `OuterQueryInterface`, `OuterAddRef`, и `OuterRelease`, наследуемых через `Base`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>CComContainedObject::AddRef  
 Увеличивает счетчик ссылок на объект-владелец.  
  
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
 [in] Объект-владелец **IUnknown**.  
  
### <a name="remarks"></a>Примечания  
 Наборы `m_pOuterUnknown` указателя на член (наследуется через `Base` класса) для `pv`.  
  
##  <a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 Деструктор  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 Возвращает `m_pOuterUnknown` указателя на член (наследуется через *базы* класса), содержащий объект-владелец **IUnknown**.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект-владелец **IUnknown**.  
  
### <a name="remarks"></a>Примечания  
 Этот метод может быть виртуальной Если `Base` объявил [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) макрос.  
  
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
 [out] Указатель на указатель на интерфейс, определяемый `iid`. Если объект не поддерживает этот интерфейс `ppvObject` равно **NULL**.  
  
 `pp`  
 [out] Указатель на указатель интерфейса, принадлежащих указанному типу `Q`. Если объект не поддерживает этот интерфейс `pp` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="release"></a>CComContainedObject::Release  
 Уменьшает счетчик ссылок на объект-владелец.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В неотладочных сборках **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
