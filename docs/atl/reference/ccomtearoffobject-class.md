---
title: "Класс CComTearOffObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
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
ms.openlocfilehash: 3e8e997f26df1adca8050bd4d967a38297685831
ms.lasthandoff: 02/24/2017

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
 Перемещаемое класс, производный от `CComTearOffObjectBase` и интерфейсы требуется объект перемещаемые для поддержки.  
  
 ATL реализует интерфейсы перемещаемые в два этапа — `CComTearOffObjectBase` методы обрабатывают счетчик ссылок и `QueryInterface`, хотя `CComTearOffObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Конструктор.|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|Увеличивает значение счетчика ссылок для `CComTearOffObject` объекта.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс в классе перемещаемые или класс-владелец.|  
|[CComTearOffObject::Release](#release)|Уменьшает счетчик ссылок для `CComTearOffObject` объекта и удаляет его.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>Методы CComTearOffObjectBase  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Конструктор.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>Члены данных CComTearOffObjectBase  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|Указатель на `CComObject` производным от класса владельца.|  
  
## <a name="remarks"></a>Примечания  
 `CComTearOffObject`реализует интерфейс перемещаемые как отдельный объект, экземпляр которого создается только в том случае, когда запрашиваются этот интерфейс. Перемещаемое удаляется, если число ссылок становится равным нулю. Как правило вы будете создавать перемещаемые интерфейс для интерфейса, который используется редко, поскольку с помощью перемещаемое сохраняет указатель vtable во всех экземплярах основного объекта.  
  
 Необходимо создать производный класс, реализующий перемещаемое из `CComTearOffObjectBase` и из любого интерфейсы должны перемещаемые объект поддержки. `CComTearOffObjectBase`шаблонизируется в классе владельца и потоковую модель. Класс-владелец является класс объекта, для которого перемещаемое реализуется. Если модель не указан, используется модель потока по умолчанию.  
  
 Следует создать сопоставление COM для класса перемещаемые. Если ATL создает перемещаемые, она создает **CComTearOffObject\<CYourTearOffClass настроек** или **CComCachedTearOffObject\<CYourTearOffClass настроек**.  
  
 Например, в Образец BEEPER `CBeeper2` – это класс, перемещаемые и `CBeeper` – это класс, владелец:  
  
 [!code-cpp[NVC_ATL_COM&#43;](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 Увеличивает счетчик ссылок `CComTearOffObject` объекта на единицу.  
  
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
 [in] Указатель, который преобразуется в указатель на **CComObject\<владелец настроек** объекта.  
  
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
 Указатель на [CComObject](../../atl/reference/ccomobject-class.md) объект, производный от *владелец*.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>Параметры  
 *Владелец*  
 [in] Класс, для которого перемещаемое реализуется.  
  
### <a name="remarks"></a>Примечания  
 Для инициализации указателя **NULL** во время построения.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор IID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Сначала запрашивает для интерфейсов класса перемещаемые. Если интерфейс не установлен, запросы для интерфейса на объекте-владельце. Если запрошенный интерфейс **IUnknown**, возвращает **IUnknown** владельца.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 Уменьшает на единицу счетчик ссылок и, если счетчик равен нулю, удаляет `CComTearOffObject`.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В сборках неотладочные всегда возвращает ноль. В отладочных построениях возвращает значение, которое может быть полезно для диагностики и тестирования.  
  
## <a name="see-also"></a>См. также  
 [Класс CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

