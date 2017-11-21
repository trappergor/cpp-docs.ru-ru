---
title: "Класс CComEnumImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumImpl
- ATLCOM/ATL::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::CComEnumImpl
- ATLCOM/ATL::CComEnumImpl::Clone
- ATLCOM/ATL::CComEnumImpl::Init
- ATLCOM/ATL::CComEnumImpl::Next
- ATLCOM/ATL::CComEnumImpl::Reset
- ATLCOM/ATL::CComEnumImpl::Skip
- ATLCOM/ATL::CComEnumImpl::m_begin
- ATLCOM/ATL::CComEnumImpl::m_dwFlags
- ATLCOM/ATL::CComEnumImpl::m_end
- ATLCOM/ATL::CComEnumImpl::m_iter
- ATLCOM/ATL::CComEnumImpl::m_spUnk
dev_langs: C++
helpviewer_keywords: CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ecc87bf670f56a2f56246cf45d2819b7ab7841f7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ccomenumimpl-class"></a>Класс CComEnumImpl
Этот класс предоставляет реализацию для COM-интерфейса перечислителя, где перечисляемые элементы хранятся в массиве.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Base,
    const IID* piid, class T, class Copy>  
class ATL_NO_VTABLE CComEnumImpl : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Перечислитель COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) интерфейса.  
  
 `piid`  
 Указатель на идентификатор интерфейса интерфейс перечислителя.  
  
 `T`  
 Тип элемента, доступные в интерфейсе перечислителя.  
  
 `Copy`  
 Однородную [скопируйте класс политики](../../atl/atl-copy-policy-classes.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Конструктор.|  
|[CComEnumImpl:: ~ CComEnumImpl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComEnumImpl::Clone](#clone)|Реализация [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx).|  
|[CComEnumImpl::Init](#init)|Инициализирует перечислитель.|  
|[CComEnumImpl::Next](#next)|Реализация [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](#reset)|Реализация [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](#skip)|Реализация [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx).|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComEnumImpl::m_begin](#m_begin)|Указатель на первый элемент в массиве.|  
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Скопируйте флаги, передаваемые через `Init`.|  
|[CComEnumImpl::m_end](#m_end)|Указатель на место сразу после последнего элемента в массиве.|  
|[CComEnumImpl::m_iter](#m_iter)|Указатель на текущий элемент в массиве.|  
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown** указатель объекта, предоставляющего перебора коллекции.|  
  
## <a name="remarks"></a>Примечания  
 `CComEnumImpl`предоставляет реализацию для COM-интерфейса перечислителя, где перечисляемые элементы хранятся в массиве. Этот класс является аналогом `IEnumOnSTLImpl` на основе класса, который предоставляет реализацию интерфейса перечислителя контейнера стандартной библиотеки C++.  
  
> [!NOTE]
>  Дополнительные сведения о дальнейшей различия между `CComEnumImpl` и `IEnumOnSTLImpl`, в разделе [CComEnumImpl::Init](#init).  
  
 Как правило, вы будете *не* необходимо создать собственный класс перечислителя путем наследования от реализации этого интерфейса. Если вы хотите использовать предоставленные ATL перечислителя на основе массива, чаще для создания экземпляра [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Тем не менее если необходимо предоставить пользовательский перечислитель (например, т.е. предоставляет интерфейсы, помимо интерфейса перечислителя), можно наследовать от этого класса. В этой ситуации, скорее всего, будет необходимо переопределить [CComEnumImpl::Clone](#clone) метод, чтобы предоставить свою собственную реализацию.  
  
 Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl  
 Конструктор.  
  
```
CComEnumImpl();
```  
  
##  <a name="dtor"></a>CComEnumImpl:: ~ CComEnumImpl  
 Деструктор  
  
```
~CComEnumImpl();
```  
  
##  <a name="init"></a>CComEnumImpl::Init  
 Перед передачей указатель на интерфейс перечислителя обратно в любых клиентов, необходимо вызвать этот метод.  
  
```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```  
  
### <a name="parameters"></a>Параметры  
 *begin*  
 Указатель на первый элемент массива, содержащего элементы для перечисления.  
  
 `end`  
 Указатель на место сразу после последнего элемента массива, содержащий элементы для перечисления.  
  
 *pUnk*  
 [in] **IUnknown** указатель объекта, который должен поддерживаться в течение времени существования перечислителя. Передайте **NULL** Если такой объект не существует.  
  
 `flags`  
 Флаги, определяющие, следует ли перечислитель стать владельцем массива или сделать его копию. Ниже описаны возможные значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывать только один раз — инициализации перечислителя, использовать его, а затем отбросить его.  
  
 Если передать указатели на объекты в массиве, которые содержатся в другой объект (и не спрашивать перечислитель для копирования данных), можно использовать *pUnk* параметр, чтобы обеспечить доступность в течение перечислитель объекта и массива, она содержит они нужны. Перечислитель просто содержит ссылку COM для объекта, чтобы поддерживать в активном состоянии. Ссылки COM автоматически освобождается при уничтожении перечислитель.  
  
 `flags` Параметр позволяет указать, как перечислитель должен интерпретировать элементы массива, переданного ему. `flags`может принимать одно из значений **CComEnumFlags** перечисления, показано ниже:  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy** означает, что время существования массива не контролируется с помощью перечислителя. В этом случае будет либо массив статического метода или объекта, указанного в *pUnk* отвечает за освобождение массив, если они больше не нужны.  
  
 **AtlFlagTakeOwnership** означает, что уничтожение массива является управление с помощью перечислителя. В этом случае массив должен были выделенную динамически с помощью **новый**. Перечислитель массива в деструкторе приведет к удалению. Как правило, следует передавать **NULL** для *pUnk*, хотя по-прежнему можно передать допустимый указатель, если требуется получать уведомления об уничтожении перечислителя по некоторым причинам.  
  
 **AtlFlagCopy** означает, что создана путем копирования массива, передаваемого в новый массив `Init`. Время существования нового массива является управляться с помощью перечислителя. Перечислитель массива в деструкторе приведет к удалению. Как правило, следует передавать **NULL** для *pUnk*, хотя по-прежнему можно передать допустимый указатель, если требуется получать уведомления об уничтожении перечислителя по некоторым причинам.  
  
> [!NOTE]
>  Прототип объекта этот метод указывает элементы массива, как оно принадлежит к типу **T**, где **T** был определен как параметр шаблона класса. Это имеет тот же тип, который предоставляется с помощью метода интерфейса COM [CComEnumImpl::Next](#next). Это то, что в отличие от [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), этот класс не поддерживает различные хранилища и предоставляемых типов данных. Тип данных элементов в массиве должен быть таким же, как тип данных, предоставляемые с помощью COM-интерфейса.  
  
##  <a name="clone"></a>CComEnumImpl::Clone  
 Этот метод предоставляет реализацию [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) метод путем создания объекта типа `CComEnum`, инициализирует его с тем же массива и итератор, используемый текущим объектом и возврат интерфейс на недавно созданном объекте.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Параметры  
 `ppEnum`  
 [out] Интерфейс на вновь созданный объект перечислителя, клонированные из текущего перечислителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что клонированный перечислители никогда не предоставляйте собственные копии (или take ownership) данные, используемые перечислителем исходного. При необходимости клонированного перечислители будет хранить исходные перечислитель активности (с помощью ссылки COM) на убедитесь, что при условии, что она необходима для данных.  
  
##  <a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 Этого интеллектуального указателя содержит ссылку на объект, передаваемый в [CComEnumImpl::Init](#init), гарантируя, что оно остается активным в течение времени существования перечислителя.  
  
```
CComPtr<IUnknown> m_spUnk;
```  
  
##  <a name="m_begin"></a>CComEnumImpl::m_begin  
 Указатель на место сразу после последнего элемента массива, содержащий элементы для перечисления.  
  
```
T* m_begin;
```  
  
##  <a name="m_end"></a>CComEnumImpl::m_end  
 Указатель на первый элемент массива, содержащего элементы для перечисления.  
  
```
T* m_end;
```  
  
##  <a name="m_iter"></a>CComEnumImpl::m_iter  
 Указатель на текущий элемент массива, содержащего элементы для перечисления.  
  
```
T* m_iter;
```  
  
##  <a name="m_dwflags"></a>CComEnumImpl::m_dwFlags  
 Флаги, передаваемый [CComEnumImpl::Init](#init).  
  
```
DWORD m_dwFlags;
```  
  
##  <a name="next"></a>CComEnumImpl::Next  
 Этот метод предоставляет реализацию [IEnumXXXX::Next](https://msdn.microsoft.com/library/ms695273.aspx) метод.  
  
```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```  
  
### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество элементов в запросе.  
  
 `rgelt`  
 [out] Массив для заполнения элементов.  
  
 `pceltFetched`  
 [out] Число элементов, фактически извлеченных в `rgelt`. Это может быть меньше, чем `celt` если менее `celt` элементы остаются в списке.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="reset"></a>CComEnumImpl::Reset  
 Этот метод предоставляет реализацию [IEnumXXXX::Reset](https://msdn.microsoft.com/library/ms693414.aspx) метод.  
  
```
STDMETHOD(Reset)(void);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="skip"></a>CComEnumImpl::Skip  
 Этот метод предоставляет реализацию [IEnumXXXX::Skip](https://msdn.microsoft.com/library/ms690392.aspx) метод.  
  
```
STDMETHOD(Skip)(ULONG celt);
```  
  
### <a name="parameters"></a>Параметры  
 `celt`  
 [in] Число пропускаемых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращает значение E_INVALIDARG, если `celt` равно нулю, возвращает значение S_FALSE, если меньше, чем `celt` элементы возвращаются, в противном случае возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [Класс CComEnum](../../atl/reference/ccomenum-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
