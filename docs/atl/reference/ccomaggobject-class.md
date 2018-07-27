---
title: Класс CComAggObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5699f4c8c49bd35e85479572e1b49f8080415e65
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884997"
---
# <a name="ccomaggobject-class"></a>Класс CComAggObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейс для объединенного объекта. По определению объединенного объекта содержится внутри внешнего объекта. `CComAggObject` Класс аналогичен [класс CComObject](../../atl/reference/ccomobject-class.md), за исключением того, что он предоставляет интерфейс, который доступен напрямую для внешних клиентов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Параметры  
 *содержится*  
 Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которую требуется поддерживать на объекте.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Конструктор.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Увеличивает счетчик ссылок на сводный объект.|  
|[CComAggObject::CreateInstance](#createinstance)|Эта статическая функция позволяет создать новую **CComAggObject <** `contained` **>** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Выполняет окончательной инициализации `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Выполняет окончательный деструкция `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComAggObject::Release](#release)|Уменьшает счетчик ссылок на сводный объект.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Делегаты `IUnknown` вызовы внешняя Неизвестная строка.|  
  
## <a name="remarks"></a>Примечания  
 `CComAggObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для объединенного объекта. `CComAggObject` имеет свой собственный `IUnknown` интерфейс, отдельно от внешнего объекта `IUnknown` интерфейс и сохраняет свой собственный счетчик ссылок.  
  
 Дополнительные сведения о статистической обработке см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>  CComAggObject::AddRef  
 Увеличивает счетчик ссылок на сводный объект.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики или тестирования.  
  
##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject  
 Конструктор.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 *PV*  
 [in] Внешняя Неизвестная строка.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComContainedObject` член, [m_contained](#m_contained)и увеличивает счетчик блокировки модуля.  
  
 Деструктор уменьшает счетчик блокировки модуля.  
  
##  <a name="dtor"></a>  CComAggObject:: ~ CComAggObject  
 Деструктор  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызовы [FinalRelease](#finalrelease), и уменьшает счетчик блокировки модуля.  
  
##  <a name="createinstance"></a>  CComAggObject::CreateInstance  
 Эта статическая функция позволяет создать новую **CComAggObject <** `contained` **>** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Параметры  
 *PP*  
 [out] Указатель на **CComAggObject\<*** содержится* **>** указатель. Если `CreateInstance` завершилась неудачно, *pp* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, назовем `AddRef` немедленно, используйте `Release` освободить ссылку на указатель на объект, когда все будет готово.  
  
 Если вы не нужен прямой доступ к объекту, но по-прежнему хотите создать новый объект без необходимости проведения `CoCreateInstance`, использовать [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо этого.  
  
##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct  
 Вызывается во время последних этапов создания объекта, этот метод выполняет инициализацию окончательный [m_contained](#m_contained) член.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="finalrelease"></a>  CComAggObject::FinalRelease  
 Вызывается во время уничтожения объекта, этот метод освобождает [m_contained](#m_contained) член.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComAggObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от этого класса.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Параметры  
 *содержится*  
 [in] Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также от любых других интерфейсов, которую требуется поддерживать на объекте.  
  
### <a name="remarks"></a>Примечания  
 Все `IUnknown` осуществляет вызов через `m_contained` делегируются внешняя Неизвестная строка.  
  
##  <a name="queryinterface"></a>  CComAggObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 *IID*  
 [in] Идентификатор запрашиваемого интерфейса.  
  
 *ppvObject*  
 [out] Указатель на указатель интерфейса, идентифицируемый *iid*. Если объект не поддерживает этот интерфейс *ppvObject* имеет значение NULL.  
  
 *PP*  
 [out] Указатель на указатель интерфейса, идентифицируемый по типу `Q`. Если объект не поддерживает этот интерфейс *pp* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Если запрошенный интерфейс `IUnknown`, `QueryInterface` возвращает указатель на объединенные объекта собственные `IUnknown` и увеличивает счетчик ссылок. В противном случае этот метод отправляет запрос для интерфейса через `CComContainedObject` член, [m_contained](#m_contained).  
  
##  <a name="release"></a>  CComAggObject::Release  
 Уменьшает счетчик ссылок на сводный объект.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных сборках `Release` возвращает значение, которое может быть полезно для диагностики или тестирования. В неотладочных сборках `Release` всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
