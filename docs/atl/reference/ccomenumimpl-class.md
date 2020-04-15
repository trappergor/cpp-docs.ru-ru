---
title: Класс CComEnumImpl
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComEnumImpl class
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
ms.openlocfilehash: 965e0a8bf6c890882754b60e2785832933d1c52c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327865"
---
# <a name="ccomenumimpl-class"></a>Класс CComEnumImpl

Этот класс обеспечивает реализацию интерфейса com enumerator, в котором перечисленные элементы хранятся в массиве.

## <a name="syntax"></a>Синтаксис

```
template <class Base,
    const IID* piid, class T, class Copy>
class ATL_NO_VTABLE CComEnumImpl : public Base
```

#### <a name="parameters"></a>Параметры

*Базы*<br/>
Интерфейс перечисления COM. См примера можно осмотреть [IEnumString.](/windows/win32/api/objidl/nn-objidl-ienumstring)

*пиид*<br/>
Указатель на идентификатор интерфейса интерфейса.

*T*<br/>
Тип элемента, выставленного интерфейсом перечисления.

*Копирование*<br/>
Однородный [класс политики копирования](../../atl/atl-copy-policy-classes.md).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComEnumImpl::CComEnumImpl](#ccomenumimpl)|Конструктор.|
|[CComEnumImpl:: CComEnumImpl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComEnumImpl:Клон](#clone)|Реализация метода интерфейса перечисления **клонов.**|
|[CComEnumImpl::Init](#init)|Инициализирует перечислитель.|
|[CComEnumImpl::Следующий](#next)|Реализация **Next**.|
|[CComEnumImpl::Перезагрузка](#reset)|Реализация **перезагрузки**.|
|[CComEnumImpl::Skip](#skip)|Реализация **Skip**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComEnumImpl::m_begin](#m_begin)|Указатель на первый элемент в массиве.|
|[CComEnumImpl::m_dwFlags](#m_dwflags)|Копировать флаги `Init`прошли через .|
|[CComEnumImpl::m_end](#m_end)|Указатель на место только за последний элемент в массиве.|
|[CComEnumImpl::m_iter](#m_iter)|Указатель на текущий элемент в массиве.|
|[CComEnumImpl::m_spUnk](#m_spunk)|Указатель `IUnknown` объекта, снабжающего коллекцию, перечисляется.|

## <a name="remarks"></a>Remarks

На примере реализации метода можно ознакомиться на [примере IEnumString.](/windows/win32/api/objidl/nn-objidl-ienumstring) `CComEnumImpl`обеспечивает реализацию интерфейса com enumerator, в котором перечисленные элементы хранятся в массиве. Этот класс аналогим `IEnumOnSTLImpl` с классом, который обеспечивает реализацию интерфейса enumerator на основе контейнера стандартной библиотеки СЗ.

> [!NOTE]
> Для получения подробной `CComEnumImpl` информации о дальнейших различиях между и `IEnumOnSTLImpl`, см. [CComEnumImpl::Init](#init).

Как правило, вам *не* нужно создавать свой собственный класс enumerator, исходя из этой реализации интерфейса. Если вы хотите использовать перенумератор, поставляемый ATL, на основе массива, чаще создается экземпляр [CComEnum.](../../atl/reference/ccomenum-class.md)

Однако, если вам нужно предоставить пользовательский регистратор (например, тот, который предоставляет интерфейсы в дополнение к интерфейсу перечисления), вы можете извлечь из этого класса. В этой ситуации, вполне вероятно, что вам нужно будет переопределить [CComEnumImpl::Клон](#clone) метод, чтобы обеспечить свою собственную реализацию.

Для получения дополнительной информации [см.](../../atl/atl-collections-and-enumerators.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComEnumImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="ccomenumimplccomenumimpl"></a><a name="ccomenumimpl"></a>CComEnumImpl::CComEnumImpl

Конструктор.

```
CComEnumImpl();
```

## <a name="ccomenumimplccomenumimpl"></a><a name="dtor"></a>CComEnumImpl:: CComEnumImpl

Деструктор

```
~CComEnumImpl();
```

## <a name="ccomenumimplinit"></a><a name="init"></a>CComEnumImpl::Init

Вы должны вызвать этот метод перед передачей указателя на интерфейс перечисления обратно к любым клиентам.

```
HRESULT Init(
    T* begin,
    T* end,
    IUnknown* pUnk,
    CComEnumFlags flags = AtlFlagNoCopy);
```

### <a name="parameters"></a>Параметры

*Начать*<br/>
Указатель на первый элемент массива, содержащий перечисленные элементы.

*end*<br/>
Указатель на место только за последним элементом массива, содержащий элементы, которые будут перечислены.

*Панк*<br/>
(в) Указатель `IUnknown` объекта, который должен быть сохранен в живых в течение всего срока службы регистратора. Передайте NULL, если такого объекта не существует.

*Флаги*<br/>
Флаги, указывающие, должен ли регистратор взять на себя ответственность за массив или сделать его копию. Возможные значения описаны ниже.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Только позвоните по этому методу один раз - инициализировать регистратор, использовать его, а затем выбросить его.

Если вы передаете указатели на элементы в массиве, хранящемся в другом объекте (и вы не просите регистратора скопировать данные), можно использовать параметр *pUnk,* чтобы гарантировать, что объект и массив, который он удерживает, доступны до тех пор, пока в них нуждается регистратор. Регистратор просто содержит ссылку COM на объект, чтобы сохранить его в живых. Ссылка COM автоматически освобождается при уничтожении регистратора.

Параметр *флагов* позволяет указать, как регистратор должен обрабатывать элементы массива, передаваемые ему. *флаги* могут взять одно из `CComEnumFlags` значений из перечисления, показанного ниже:

```
enum CComEnumFlags
   {
   AtlFlagNoCopy = 0,
   AtlFlagTakeOwnership = 2, // BitOwn
   AtlFlagCopy = 3           // BitOwn | BitCopy
   };
```

`AtlFlagNoCopy`означает, что срок службы массива не контролируется регистратором. В этом случае либо массив будет статичным, либо объект, идентифицированный *pUnk,* будет отвечать за освобождение массива, когда он больше не нужен.

`AtlFlagTakeOwnership`означает, что разрушение массива должно контролироваться регистратором. В этом случае массив должен быть динамически выделен с помощью **нового.** Регистратор удалит массив в его деструкторе. Как правило, вы бы пройти NULL для *pUnk*, хотя вы все еще можете пройти действительный указатель, если вам нужно быть уведомлены об уничтожении регистратора по некоторым причинам.

`AtlFlagCopy`означает, что новый массив должен быть создан `Init`путем копирования массива, передаваемого в . Срок службы нового массива должен контролироваться регистратором. Регистратор удалит массив в его деструкторе. Как правило, вы бы пройти NULL для *pUnk*, хотя вы все еще можете пройти действительный указатель, если вам нужно быть уведомлены об уничтожении регистратора по некоторым причинам.

> [!NOTE]
> Прототип этого метода определяет элементы массива как `T`тип, где `T` был определен как параметр шаблона для класса. Это тот же тип, который подвергается с помощью метода интерфейса COM [CComEnumImpl::Следующий](#next). Смысл этого заключается в том, что, в отличие от [IEnumOnSTLImpl,](../../atl/reference/ienumonstlimpl-class.md)этот класс не поддерживает различные типы хранения и открытых данных. Тип элементов в массиве данных должен быть таким же, как и тип данных, разоблачаемый с помощью интерфейса COM.

## <a name="ccomenumimplclone"></a><a name="clone"></a>CComEnumImpl:Клон

Этот метод обеспечивает реализацию метода **клона** путем `CComEnum`создания объекта типа, инициализации его с тем же массивом и итератором, используемым текущим объектом, и возвращения интерфейса на вновь созданный объект.

```
STDMETHOD(Clone)(Base** ppEnum);
```

### <a name="parameters"></a>Параметры

*ppEnum*<br/>
(ваут) Интерфейс перечисления на недавно созданном объекте, клонированном из текущего регистратора.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Обратите внимание, что клонированные регистраторы никогда не делают свою собственную копию (или взять на себя ответственность) данных, используемых исходным регистратором. При необходимости клонированные регистраторы сохранят исходный регистратор (с использованием ссылки COM), чтобы гарантировать, что данные доступны до тех пор, пока они в них нуждаются.

## <a name="ccomenumimplm_spunk"></a><a name="m_spunk"></a>CComEnumImpl::m_spUnk

Этот умный указатель поддерживает ссылку на объект, передаваемый [CComEnumImpl::Init](#init), гарантируя, что он остается живым в течение всего срока службы регистратора.

```
CComPtr<IUnknown> m_spUnk;
```

## <a name="ccomenumimplm_begin"></a><a name="m_begin"></a>CComEnumImpl::m_begin

Указатель на место только за последним элементом массива, содержащий элементы, которые будут перечислены.

```
T* m_begin;
```

## <a name="ccomenumimplm_end"></a><a name="m_end"></a>CComEnumImpl::m_end

Указатель на первый элемент массива, содержащий перечисленные элементы.

```
T* m_end;
```

## <a name="ccomenumimplm_iter"></a><a name="m_iter"></a>CComEnumImpl::m_iter

Указатель на текущий элемент массива, содержащий перечисленные элементы.

```
T* m_iter;
```

## <a name="ccomenumimplm_dwflags"></a><a name="m_dwflags"></a>CComEnumImpl::m_dwFlags

Флаги перешли к [CComEnumImpl::: Init](#init).

```
DWORD m_dwFlags;
```

## <a name="ccomenumimplnext"></a><a name="next"></a>CComEnumImpl::Следующий

Этот метод обеспечивает реализацию **следующего** метода.

```
STDMETHOD(Next)(ULONG celt, T* rgelt, ULONG* pceltFetched);
```

### <a name="parameters"></a>Параметры

*celt*<br/>
(в) Количество запрошенных элементов.

*Rgelt*<br/>
(ваут) Массив, который должен быть заполнен элементами.

*pceltFetched*<br/>
(ваут) Количество элементов фактически возвращается в *rgelt*. Это может быть меньше, чем *кельт,* если меньше, чем *элементы кельта* остались в списке.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomenumimplreset"></a><a name="reset"></a>CComEnumImpl::Перезагрузка

Этот метод обеспечивает реализацию метода **сбросить.**

```
STDMETHOD(Reset)(void);
```

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

## <a name="ccomenumimplskip"></a><a name="skip"></a>CComEnumImpl::Skip

Этот метод обеспечивает реализацию метода **Skip.**

```
STDMETHOD(Skip)(ULONG celt);
```

### <a name="parameters"></a>Параметры

*celt*<br/>
(в) Количество элементов, чтобы пропустить.

### <a name="return-value"></a>Возвращаемое значение

Стандартное значение HRESULT.

### <a name="remarks"></a>Remarks

Возвращает E_INVALIDARG если *кельт* равен нулю, возвращается S_FALSE, если возвращается меньше элементов *кельта,* возвращается S_OK в противном случае.

## <a name="see-also"></a>См. также раздел

[Класс IenumOnSTLimpl](../../atl/reference/ienumonstlimpl-class.md)<br/>
[Класс CComEnum](../../atl/reference/ccomenum-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
