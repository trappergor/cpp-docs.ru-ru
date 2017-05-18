---
title: "Класс CComEnumImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 6dc6a8ed6a318642efe58dfb94835d45b2163b54
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumimpl-class"></a>Класс CComEnumImpl
Этот класс предоставляет реализацию для интерфейса COM перечислителя, где хранятся перечисляемых элементов в массиве.  
  
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
 Тип элемента, предоставляемых интерфейсом перечислителя.  
  
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
|[CComEnumImpl::m_spUnk](#m_spunk)|**IUnknown** указатель объекта, указав перечисляемой коллекции.|  
  
## <a name="remarks"></a>Примечания  
 `CComEnumImpl`предоставляет реализацию для интерфейса COM перечислителя, где хранятся перечисляемых элементов в массиве. Этот класс является аналогом `IEnumOnSTLImpl` класс, который предоставляет реализацию интерфейса перечислителя на основании контейнера стандартной библиотеки C++.  
  
> [!NOTE]
>  Дополнительные сведения о дальнейшей различия между `CComEnumImpl` и `IEnumOnSTLImpl`, в разделе [CComEnumImpl::Init](#init).  
  
 Как правило, будет *не* необходимо создать собственный класс перечислителя путем наследования от реализации этого интерфейса. Если вы хотите использовать предоставленные ATL перечислителя на основе массива, чаще для создания экземпляра [CComEnum](../../atl/reference/ccomenum-class.md).  
  
 Тем не менее если необходимо предоставить пользовательский перечислитель (например, по одному, предоставляет интерфейсы, кроме интерфейса перечислителя), могут наследовать от этого класса. В этом случае, вероятно, будет необходимо переопределить [CComEnumImpl::Clone](#clone) метод, чтобы предоставить свою собственную реализацию.  
  
 Дополнительные сведения см. в разделе [коллекции и перечислители ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComEnumImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
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
 Прежде чем передать указатель на интерфейс перечислителя обратно для любых клиентов, необходимо вызвать этот метод.  
  
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
 Флаги, определяющие, следует ли перечислитель стать владельцем массива или сделать его копию. Возможные значения описаны ниже.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывать только один раз — инициализации перечислителя, использовать его, а затем выбрасывайте ее.  
  
 Если передать указатели на объекты в массиве, содержащихся в другом объекте (и не спрашивайте перечислитель для копирования данных), можно использовать *pUnk* параметр убедитесь что объекта и массива, он содержит доступны для до тех пор, пока они нужны перечислитель. Перечислитель просто хранит ссылку COM для объекта, чтобы поддерживать в активном состоянии. Ссылки COM автоматически освобождается при уничтожении перечислитель.  
  
 `flags` Позволяет указать, как перечислитель следует рассматривать элементы массива, переданного ему. `flags`может принимать одно из значений **CComEnumFlags** перечисления, показано ниже:  
  
```  
enum CComEnumFlags  
   {  
   AtlFlagNoCopy = 0,  
   AtlFlagTakeOwnership = 2, // BitOwn  
   AtlFlagCopy = 3           // BitOwn | BitCopy  
   };  
```  
  
 **AtlFlagNoCopy** означает, что время существования массива не управляются с помощью перечислителя. В этом случае либо массив будет иметь статический метод или объекта, указанного в *pUnk* отвечает за освобождение массива, когда он больше не нужен.  
  
 **AtlFlagTakeOwnership** означает, что уничтожение массива является управление с помощью перечислителя. В этом случае массив необходимо динамически занятых с помощью **новый**. Перечислитель удалит массива в деструкторе. Как правило, следует передавать **NULL** для *pUnk*, хотя по-прежнему можно передать допустимый указатель, если требуется получать уведомления о уничтожения перечислитель по некоторым причинам.  
  
 **AtlFlagCopy** означает, что новый массив с копирование массива, передаваемый `Init`. Время существования нового массива — управляться с помощью перечислителя. Перечислитель удалит массива в деструкторе. Как правило, следует передавать **NULL** для *pUnk*, хотя по-прежнему можно передать допустимый указатель, если требуется получать уведомления о уничтожения перечислитель по некоторым причинам.  
  
> [!NOTE]
>  Прототип этот метод задает элементы массива как типа **T**, где **T** был определен в качестве параметра шаблона в класс. Это же тип, который предоставляется с помощью метода интерфейса COM [CComEnumImpl::Next](#next). Это то, что в отличие от [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md), этот класс не поддерживает различные хранилища и представлены типы данных. Тип данных элементов в массиве должно быть таким же, как тип данных, предоставляемый посредством COM-интерфейса.  
  
##  <a name="clone"></a>CComEnumImpl::Clone  
 Этот метод предоставляет реализацию [IEnumXXXX::Clone](https://msdn.microsoft.com/library/ms690336.aspx) метод путем создания объекта типа `CComEnum`, инициализирует его с тем же массива и итератор, используемый текущим объектом и возвращает интерфейс на вновь созданный объект.  
  
```
STDMETHOD(Clone)(Base** ppEnum);
```  
  
### <a name="parameters"></a>Параметры  
 `ppEnum`  
 [out] Интерфейс на вновь созданный объект перечислителя, клонированные из текущего перечислителя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, что клонированный перечислители никогда не предоставляйте собственные копии (или Смена владельца) данные, используемые исходные перечислителя. При необходимости клонированный перечислители будет активности исходного перечислитель (используя ссылку COM), чтобы обеспечить доступность для данных при условии, что им.  
  
##  <a name="m_spunk"></a>CComEnumImpl::m_spUnk  
 Этого интеллектуального указателя содержит ссылку на объект, передаваемый в [CComEnumImpl::Init](#init), гарантируя, что он остается активным в течение времени существования перечислителя.  
  
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
 Указатель текущего элемента массива, содержащего элементы для перечисления.  
  
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
 [in] Число элементов в запросе.  
  
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
 Возвращает значение E_INVALIDARG, если `celt` равно нулю, возвращает значение S_FALSE, если меньше чем `celt` элементы возвращаются, в противном случае возвращает значение S_OK.  
  
## <a name="see-also"></a>См. также  
 [Класс IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [Класс CComEnum](../../atl/reference/ccomenum-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

