---
title: "Класс CComObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27da00e09ca88cc06b8bafed8f8601dac756fd34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomobject-class"></a>Класс CComObject
Этот класс реализует **IUnknown** неагрегированные объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любых других интерфейсов, которые требуется поддерживать на объект.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Конструктор.|  
|[CComObject:: ~ CComObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Увеличивает счетчик ссылок на объект.|  
|[CComObject::CreateInstance](#createinstance)|(Статический) Создает новый `CComObject` объекта.|  
|[CComObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComObject::Release](#release)|Уменьшает счетчик ссылок на объект.|  
  
## <a name="remarks"></a>Примечания  
 `CComObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) неагрегированные объекта. Однако вызовы `QueryInterface`, `AddRef`, и **выпуска** делегируются `CComObjectRootEx`.  
  
 Дополнительные сведения об использовании `CComObject`, см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>CComObject::AddRef  
 Увеличивает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает новый счетчик увеличивается ссылок на объект. Это значение может быть полезен для диагностики и тестирования.  
  
##  <a name="ccomobject"></a>CComObject::CComObject  
 Конструктор увеличивает счетчик блокировки модуля.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 **void\***  
 [in] Это Неименованный параметр не используется. Он существует для симметрии с другими **CCom***XXX*`Object`*XXX* конструкторы.  
  
### <a name="remarks"></a>Примечания  
 Деструктор уменьшает его.  
  
 Если `CComObject`-успешно производного объекта создается с помощью **новый** оператор, начальное значение счетчика ссылок равно 0. Устанавливает значение счетчика ссылок на соответствующее значение (1), чтобы вызов [AddRef](#addref) функции.  
  
##  <a name="dtor"></a>CComObject:: ~ CComObject  
 Деструктор  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызовы [FinalRelease](ccomobjectrootex-class.md#finalrelease), и уменьшает счетчик блокировки модуля.  

  
##  <a name="createinstance"></a>CComObject::CreateInstance  
 Эта статическая функция позволяет создать новую **CComObject <** `Base`  **>**  объекта, одновременно снижая издержки [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `pp`  
 [out] Указатель на **CComObject <** `Base`  **>**  указателя. Если `CreateInstance` завершается неудачно, `pp` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, поэтому вызовов `AddRef` немедленно, воспользуйтесь **выпуска** освободить ссылку на указатель на объект после завершения.  
  
 Если не требуется прямой доступ к объекту, но все равно хотите создать новый объект без необходимости проведения `CoCreateInstance`, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо него.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#38](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM#39](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="release"></a>CComObject::Release  
 Уменьшает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает новый счетчик ссылок уменьшается на единицу для объекта. В отладочных построениях возвращаемое значение может быть полезно для диагностики или тестирования. В неотладочных сборках **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
