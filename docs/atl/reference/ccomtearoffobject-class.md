---
title: "Класс CComTearOffObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs: C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80be7d80af5a6c8fa2c47bc0e853020663f2ceae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomtearoffobject-class"></a>Класс CComTearOffObject
Этот класс реализует интерфейс перемещаемые.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Перемещаемые класс, производный от `CComTearOffObjectBase` и интерфейсы нужно объекта перемещаемые для поддержки.  
  
 ATL реализует интерфейсы перемещаемые в два этапа — `CComTearOffObjectBase` методы обрабатывают счетчик ссылок и `QueryInterface`, пока `CComTearOffObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Конструктор.|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|Увеличивает счетчик ссылок для `CComTearOffObject` объекта.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс на перемещаемые класс или класс-владелец.|  
|[CComTearOffObject::Release](#release)|Уменьшает счетчик ссылок для `CComTearOffObject` объекта и удаляет его.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>Методы CComTearOffObjectBase  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Конструктор.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>Члены данных CComTearOffObjectBase  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|Указатель на `CComObject` производный от класса владельца.|  
  
## <a name="remarks"></a>Примечания  
 `CComTearOffObject`реализует интерфейс перемещаемые как отдельный объект, экземпляр которого создается только в том случае, когда запрашиваются этот интерфейс. Перемещаемое удаляется, если число ссылок становится равным нулю. Как правило при построении перемещаемые интерфейса для интерфейса, который используется редко, так как с помощью перемещаемое сохраняет указатель vtable во всех экземплярах основного объекта.  
  
 Необходимо создать производный класс, реализующий перемещаемое из `CComTearOffObjectBase` и из любого интерфейсы должны объекта перемещаемые для поддержки. `CComTearOffObjectBase`шаблонизируется класс-владелец и потоковую модель. Класс владельца является класс объекта, для которого перемещаемое реализуется. Если модель не указан, используется модель потока по умолчанию.  
  
 Необходимо создать сопоставление COM для класса перемещаемые. Когда перемещаемое создает ATL, он создаст **CComTearOffObject\<CYourTearOffClass >** или **CComCachedTearOffObject\<CYourTearOffClass >**.  
  
 Например, в Образец BEEPER `CBeeper2` класс является перемещаемой и `CBeeper` класс является владелец:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 Увеличивает число ссылок `CComTearOffObject` объекта на единицу.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 Конструктор.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Указатель, который преобразуется в указатель на **CComObject\<владельца >** объекта.  
  
### <a name="remarks"></a>Примечания  
 Увеличивает счетчик ссылок владельца на единицу.  
  
##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject  
 Деструктор  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызывающий модуль FinalRelease и уменьшает счетчик блокировки.  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 Конструктор.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует [m_pOwner](#m_powner) члена **NULL**.  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 Указатель на [CComObject](../../atl/reference/ccomobject-class.md) объект, производный от *владельца*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Параметры  
 *Владелец*  
 [in] Класс, для которого перемещаемое реализуется.  
  
### <a name="remarks"></a>Примечания  
 При инициализации указатель **NULL** во время построения.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор IID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель на интерфейс, определяемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Сначала запрашивает для интерфейсов класса перемещаемые. Если интерфейс не установлен, запросы для интерфейса на объект-владелец. Если запрошенный интерфейс **IUnknown**, возвращает **IUnknown** владельца.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 Уменьшает число ссылок на единицу и, если счетчик ссылок равен нулю, удаляет `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В неотладочных сборках всегда возвращает ноль. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
