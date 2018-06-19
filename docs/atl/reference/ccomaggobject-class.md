---
title: Класс CComAggObject | Документы Microsoft
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
ms.openlocfilehash: 426a01c1957b276174b8b36884605b69dd501de8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364223"
---
# <a name="ccomaggobject-class"></a>Класс CComAggObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейс для вычисляемого объекта. По определению вычисляемого объекта внутри внешнего объекта. `CComAggObject` Класс аналогичен [CComObject класса](../../atl/reference/ccomobject-class.md), за исключением того, что он предоставляет интерфейс, который напрямую доступны для внешних клиентов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Параметры  
 `contained`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любых других интерфейсов, которые требуется поддерживать на объект.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Конструктор.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Увеличивает счетчик ссылок на статистические объекта.|  
|[CComAggObject::CreateInstance](#createinstance)|Эта статическая функция позволяет создать новую **CComAggObject <** `contained` **>** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Выполняет окончательной инициализации `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Выполняет окончательного удаления `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComAggObject::Release](#release)|Уменьшает счетчик ссылок на статистические объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Делегаты `IUnknown` вызовы внешняя Неизвестная строка.|  
  
## <a name="remarks"></a>Примечания  
 `CComAggObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для вычисляемого объекта. `CComAggObject` имеет свой собственный **IUnknown** интерфейс, отдельно от внешнего объекта **IUnknown** интерфейс, а также поддерживает число ссылок.  
  
 Дополнительные сведения о статистической обработки см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>  CComAggObject::AddRef  
 Увеличивает счетчик ссылок на статистические объекта.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject  
 Конструктор.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
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
 `pp`  
 [out] Указатель на **CComAggObject\<*** содержится* **>** указателя. Если `CreateInstance` завершается неудачно, `pp` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, поэтому вызовов `AddRef` немедленно, воспользуйтесь **выпуска** освободить ссылку на указатель на объект после завершения.  
  
 Если не требуется прямой доступ к объекту, но все равно хотите создать новый объект без необходимости проведения `CoCreateInstance`, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо него.  
  
##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct  
 Вызывается во время последних этапов создания объекта, этот метод выполняет инициализацию окончательного [m_contained](#m_contained) член.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="finalrelease"></a>  CComAggObject::FinalRelease  
 Вызывается при уничтожении объекта, этот метод освобождает [m_contained](#m_contained) член.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComAggObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от класса.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Параметры  
 `contained`  
 [in] Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любых других интерфейсов, которые требуется поддерживать на объект.  
  
### <a name="remarks"></a>Примечания  
 Все **IUnknown** вызывается с помощью `m_contained` делегируются внешняя Неизвестная строка.  
  
##  <a name="queryinterface"></a>  CComAggObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
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
  
### <a name="remarks"></a>Примечания  
 Если запрошенный интерфейс **IUnknown**, `QueryInterface` возвращает указатель на статистические объекта собственные **IUnknown** и увеличивает счетчик ссылок. В противном случае этот метод запрашивает интерфейс через `CComContainedObject` член, [m_contained](#m_contained).  
  
##  <a name="release"></a>  CComAggObject::Release  
 Уменьшает счетчик ссылок на статистические объекта.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В неотладочных сборках **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
