---
title: "Класс IEnumOnSTLImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl
- ATLCOM/ATL::IEnumOnSTLImpl::Clone
- ATLCOM/ATL::IEnumOnSTLImpl::Init
- ATLCOM/ATL::IEnumOnSTLImpl::Next
- ATLCOM/ATL::IEnumOnSTLImpl::Reset
- ATLCOM/ATL::IEnumOnSTLImpl::Skip
- ATLCOM/ATL::IEnumOnSTLImpl::m_iter
- ATLCOM/ATL::IEnumOnSTLImpl::m_pcollection
- ATLCOM/ATL::IEnumOnSTLImpl::m_spUnk
dev_langs:
- C++
helpviewer_keywords:
- IEnumOnSTLImpl class
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
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
ms.openlocfilehash: 291993d2914d6082b69bfe7816d7c805e93494c4
ms.lasthandoff: 02/24/2017

---
# <a name="ienumonstlimpl-class"></a>Класс IEnumOnSTLImpl
Этот класс определяет интерфейс перечислителя на основе коллекции стандартной библиотеки C++.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType>  
class ATL_NO_VTABLE IEnumOnSTLImpl : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Перечислитель COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) интерфейса.  
  
 `piid`  
 Указатель на идентификатор интерфейса интерфейс перечислителя.  
  
 `T`  
 Тип элемента, предоставляемых интерфейсом перечислителя.  
  
 `Copy`  
 Объект [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 Класс контейнеров стандартной библиотеки C++.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](#clone)|Реализация [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](#init)|Инициализирует перечислитель.|  
|[IEnumOnSTLImpl::Next](#next)|Реализация [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](#reset)|Реализация [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](#skip)|Реализация [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m_iter](#m_iter)|Итератор, который представляет перечислителя из текущей позиции в коллекции.|  
|[IEnumOnSTLImpl::m_pcollection](#m_pcollection)|Указатель на стандартную библиотеку C++ контейнера, содержащего элементы для перечисления.|  
|[IEnumOnSTLImpl::m_spUnk](#m_spunk)|**IUnknown** указатель объекта, указав коллекцию.|  
  
## <a name="remarks"></a>Примечания  
 `IEnumOnSTLImpl`предоставляет реализацию для интерфейса COM перечислителя, где хранятся перечисляемых элементов в контейнере совместимые библиотеки C++ Standard. Этот класс является аналогом [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md) класс, который предоставляет реализацию для интерфейса перечислителя на основе массива.  
  
> [!NOTE]
>  В разделе [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init) сведения о дальнейшей различия между `CComEnumImpl` и `IEnumOnSTLImpl`.  
  
 Как правило, будет *не* необходимо создать собственный класс перечислителя путем наследования от реализации этого интерфейса. Если вы хотите использовать перечислитель предоставляемый ATL, основанное на контейнере стандартной библиотеки C++, чаще для создания экземпляра [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md), или для создания класса коллекции, который возвращает перечислитель, производные от [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  
  
 Тем не менее если необходимо предоставить пользовательский перечислитель (например, по одному, предоставляет интерфейсы, кроме интерфейса перечислителя), могут наследовать от этого класса. В этом случае вполне вероятно, что необходимо переопределить [клон](#clone) метод, чтобы предоставить свою собственную реализацию.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="init"></a>IEnumOnSTLImpl::Init  
 Инициализирует перечислитель.  
  
```
HRESULT Init(
    IUnknown* pUnkForRelease,
    CollType& collection);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkForRelease`  
 [in] **IUnknown** указатель объекта, который должен поддерживаться в течение времени существования перечислителя. Передайте **NULL** Если такой объект не существует.  
  
 `collection`  
 Ссылка на контейнер стандартной библиотеки C++, который содержит элементы для перечисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если передать `Init` ссылку на коллекцию, хранящиеся в другой объект, можно использовать `pUnkForRelease` обеспечивает, что объекта и коллекции, он содержит будет доступен до тех пор, пока она нужна перечислитель параметр.  
  
 Прежде чем передать указатель на интерфейс перечислителя обратно для любых клиентов, необходимо вызвать этот метод.  
  
##  <a name="clone"></a>IEnumOnSTLImpl::Clone  
 Этот метод предоставляет реализацию [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) метод путем создания объекта типа `CComEnumOnSTL`, инициализирует его с тем же коллекции и итераторов, используемые текущим объектом и возвращает интерфейс на вновь созданный объект.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Параметры  
 `ppEnum`  
 [out] Интерфейс на вновь созданный объект перечислителя, клонированные из текущего перечислителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="m_spunk"></a>IEnumOnSTLImpl::m_spUnk  
 **IUnknown** указатель объекта, указав коллекцию.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
### <a name="remarks"></a>Примечания  
 Этого интеллектуального указателя содержит ссылку на объект, передаваемый в [IEnumOnSTLImpl::Init](#init), гарантируя, что он остается активным в течение времени существования перечислителя.  
  
##  <a name="m_pcollection"></a>IEnumOnSTLImpl::m_pcollection  
 Этот элемент указывает коллекцию, которая содержит данные, представленные реализацию интерфейса перечислителя.  
  
```
CollType* m_pcollection;
```  
  
### <a name="remarks"></a>Примечания  
 Этот член инициализируется путем вызова [IEnumOnSTLImpl::Init](#init).  
  
##  <a name="m_iter"></a>IEnumOnSTLImpl::m_iter  
 Этот член содержит итератора, который используется для маркировки текущую позицию в коллекции и перехода на последующие элементы.  
  
```
CollType::iterator m_iter;
```  
  
##  <a name="next"></a>IEnumOnSTLImpl::Next  
 Этот метод предоставляет реализацию [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) метод.  
  
```
STDMETHOD(Next)(
    ULONG celt,
    T* rgelt,
    ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Число элементов в запросе.  
  
 `rgelt`  
 [out] Массив, который заполняется элементы.  
  
 `pceltFetched`  
 [out] Число элементов, фактически извлеченных в `rgelt`. Это может быть меньше, чем `celt` если менее `celt` элементы остаются в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="reset"></a>IEnumOnSTLImpl::Reset  
 Этот метод предоставляет реализацию [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) метод.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="skip"></a>IEnumOnSTLImpl::Skip  
 Этот метод предоставляет реализацию [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) метод.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Число пропускаемых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

