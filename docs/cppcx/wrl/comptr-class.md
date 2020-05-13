---
title: Класс ComPtr
ms.date: 07/26/2019
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
ms.openlocfilehash: 89c09ede972f5bdd5da1dde810cad31733bdf338
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372639"
---
# <a name="comptr-class"></a>Класс ComPtr

Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. `ComPtr` автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Интерфейс, который `ComPtr` представляет.

*U*<br/>
Класс, к которому ток `ComPtr` является другом. (Шаблон, который использует этот параметр, защищен.)

## <a name="remarks"></a>Remarks

`ComPtr<>`объявляет тип, представляющий основной указатель интерфейса. Используйте `ComPtr<>` для объявления переменной, а затем`->`используйте оператора доступа к функции члена интерфейса стрелка () для доступа к функции члена интерфейса.

Более подробную информацию об интеллектуальных указателях можно ознакомьтесь с подразделом "COM Smart Pointers" [в](/windows/win32/LearnWin32/com-coding-practices) библиотеке MSDN.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя            | Описание
--------------- | ---------------------------------------------------------------
`InterfaceType` | Синоним типа, указанного параметром шаблона *T.*

### <a name="public-constructors"></a>Открытые конструкторы

Имя                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:ComPtr](#comptr)        | Инициализирует новый экземпляр класса `ComPtr`. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.
[ComPtr:::ComPtr](#tilde-comptr) | Деприонизутирует `ComPtr`экземпляр .

### <a name="public-methods"></a>Открытые методы

Имя                                                      | Описание
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | Возвращает `ComPtr` объект, представляющий интерфейс, идентифицированный указанным параметром шаблона.
[ComPtr::ASIID](#asiid)                                   | Возвращает `ComPtr` объект, представляющий интерфейс, идентифицированный указанным идентификатором интерфейса.
[ComPtr::Asweak](#asweak)                                 | Извлекает слабую ссылку на текущий объект.
[ComPtr::Attach](#attach)                                 | Связывает это `ComPtr` с типом интерфейса, указанным текущим параметром типа шаблона.
[ComPtr::CopyTo](#copyto)                                 | Копирует текущий или указанный `ComPtr` интерфейс, связанный с этим, в указанный указатель вывода.
[ComPtr::Detach](#detach)                                 | Отсажает `ComPtr` это от интерфейса, который он представляет.
[ComPtr::Get](#get)                                       | Извлекает указатель на интерфейс, который `ComPtr`связан с этим.
[ComPtr::GetAddressOf](#getaddressof)                     | Извлекает адрес ptr_ участника [данных,](#ptr) который содержит указатель на `ComPtr`интерфейс, представленный этим .
[ComPtr::ReleaseandgetAddressof](#releaseandgetaddressof) | Выпускает интерфейс, связанный с этим, `ComPtr` а затем извлекает адрес [ptr_](#ptr) члена данных, который содержит указатель на выпущенный интерфейс.
[ComPtr::Reset](#reset)                                   | Выпускает все ссылки для указателя на интерфейс, `ComPtr`который связан с этим.
[ComPtr::Swap](#swap)                                     | Обменивает интерфейс, управляемый `ComPtr` током, с `ComPtr`интерфейсом, управляемым указанным.

### <a name="protected-methods"></a>Защищенные методы

Имя                                        | Описание
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr::InternalAddRef](#internaladdref)   | Приращения эталонного количества интерфейса, связанного с этим. `ComPtr`
[ComPtr::InternalRelease](#internalrelease) | Выполняет операцию COM Release на интерфейсе, связанном с этим. `ComPtr`

### <a name="public-operators"></a>Открытые операторы

Имя                                                                                           | Описание
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr::оператор&](#operator-ampersand)                                                       | Извлекает адрес текущего `ComPtr`.
[ComPtr::оператор->](#operator-arrow)                                                          | Извлекает указатель на тип, заданный текущим параметром шаблона.
[ComPtr::оператор](#operator-assign)                                                          | Присваивает значение `ComPtr`текущему.
[ComPtr::оператор](#operator-equality)                                                       | Определение равенства двух объектов `ComPtr`.
[ComPtr::оператор!](#operator-inequality)                                                     | Определяет неравенство двух объектов `ComPtr`.
[ComPtr::оператор Microsoft::WRL::D::BoolType](#operator-microsoft-wrl-details-booltype) | Указывает, управляет `ComPtr` ли человек сроком службы интерфейса объекта.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                 | Описание
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr](#ptr) | Содержит указатель на интерфейс, который связан с `ComPtr`этим и управляется им.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>ComPtr:::ComPtr

Деприонизутирует `ComPtr`экземпляр .

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>ComPtr::As

Возвращает `ComPtr` объект, представляющий интерфейс, идентифицированный указанным параметром шаблона.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>Параметры

*U*<br/>
Интерфейс, который будет представлен по параметру *p*.

*P*<br/>
Объект, `ComPtr` представляющий интерфейс, указанный по параметру *U.* Параметр *p* не должен `ComPtr` относиться к текущему объекту.

### <a name="remarks"></a>Remarks

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="comptrasiid"></a><a name="asiid"></a>ComPtr::ASIID

Возвращает `ComPtr` объект, представляющий интерфейс, идентифицированный указанным идентификатором интерфейса.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*P*<br/>
Если объект имеет интерфейс, идентификатор которого равен *riid,* двойной косвенный указатель на интерфейс, указанный *параметром riid;* в противном случае, указатель на `IUnknown`.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="comptrasweak"></a><a name="asweak"></a>ComPtr::Asweak

Извлекает слабую ссылку на текущий объект.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Параметры

*pWeakRef*<br/>
После завершения операции представляет указатель на объект слабой ссылки.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="comptrattach"></a><a name="attach"></a>ComPtr::Attach

Связывает это `ComPtr` с типом интерфейса, указанным текущим параметром типа шаблона.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Тип интерфейса.

## <a name="comptrcomptr"></a><a name="comptr"></a>ComPtr:ComPtr

Инициализирует новый экземпляр класса `ComPtr`. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.

```cpp
WRL_NOTHROW ComPtr();

WRL_NOTHROW ComPtr(
   decltype(__nullptr)
);

template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);

WRL_NOTHROW ComPtr(
   const ComPtr& other
);

template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);

WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);

template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other, typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);
```

### <a name="parameters"></a>Параметры

*U*<br/>
Тип *другого* параметра.

*Других*<br/>
Объект типа *U*.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Первым конструктором является конструктор по умолчанию, который подразумевает создание пустого объекта. Второй конструктор указывает [__nullptr,](../../extensions/nullptr-cpp-component-extensions.md)который явно создает пустой объект.

Третий конструктор создает объект из объекта, указанного указателем. ComPtr теперь владеет остроконечной памятью и поддерживает подсчет ссылок на нее.

Четвертый и пятый конструкторы являются копироваторами. Пятый конструктор копирует объект, если он конвертируется в текущий тип.

Шестой и седьмой конструкторы являются переместить конструкторов. Седьмой конструктор перемещает объект, если он кабриолет к текущему типу.

## <a name="comptrcopyto"></a><a name="copyto"></a>ComPtr::CopyTo

Копирует текущий или указанный `ComPtr` интерфейс, связанный с этим, в указанный указатель.

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>Параметры

*U*<br/>
Имя типа.

*Ptr*<br/>
После завершения операции представляет указатель на запрошенный интерфейс.

*riid*<br/>
Идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, HRESULT, который указывает, почему неявная `QueryInterface` операция не удалось.

### <a name="remarks"></a>Remarks

Первая функция возвращает копию указателя в интерфейс, связанный с этим. `ComPtr` Эта функция всегда возвращает значение S_OK.

Вторая функция выполняет `QueryInterface` операцию на интерфейсе, связанном с этим `ComPtr` для интерфейса, указанного параметром *riid.*

Третья функция выполняет `QueryInterface` операцию на интерфейсе, связанном с этим `ComPtr` для базового интерфейса параметра *U.*

## <a name="comptrdetach"></a><a name="detach"></a>ComPtr::Detach

Отменяет связь этого объекта `ComPtr` с интерфейсом, который он представляет.

```cpp
T* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который был представлен этим объектом `ComPtr`.

## <a name="comptrget"></a><a name="get"></a>ComPtr::Get

Извлекает указатель на интерфейс, который `ComPtr`связан с этим.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который `ComPtr`связан с этим.

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>ComPtr::GetAddressOf

Извлекает адрес ptr_ участника [данных,](#ptr) который содержит указатель на `ComPtr`интерфейс, представленный этим .

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес переменной.

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>ComPtr::InternalAddRef

Приращения эталонного количества интерфейса, связанного с этим. `ComPtr`

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Remarks

Этот метод защищен.

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>ComPtr::InternalRelease

Выполняет операцию COM Release на интерфейсе, связанном с этим. `ComPtr`

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Remarks

Этот метод защищен.

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>ComPtr:оператор&amp;

Освобождает интерфейс, связанный с этим объектом `ComPtr`, а затем извлекает адрес объекта `ComPtr`.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Возвращаемое значение

Слабая ссылка на текущий объект `ComPtr`.

### <a name="remarks"></a>Remarks

Этот метод отличается от [ComPtr::GetAddressOf](#getaddressof) в том, что этот метод выпускает ссылку на указатель интерфейса. Используйте метод `ComPtr::GetAddressOf`, если необходим адрес указателя интерфейса, но этот интерфейс освобождать не требуется.

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>ComPtr::оператор-&gt;

Извлекает указатель на тип, заданный текущим параметром шаблона.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на тип, заданный текущим именем типа шаблона.

### <a name="remarks"></a>Remarks

Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция `IUnknown` `private` делает `virtual`типы вместо .

## <a name="comptroperator"></a><a name="operator-assign"></a>ComPtr::оператор

Присваивает значение `ComPtr`текущему.

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>Параметры

*U*<br/>
Класс.

*Других*<br/>
Указатель, ссылка или rvalue ссылка `ComPtr`на тип или другой .

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `ComPtr`текущий .

### <a name="remarks"></a>Remarks

Первая версия этого оператора присваивает `ComPtr`текущее значение пустому значению.

Во второй версии, если указатель интерфейса присваивается не совпадает с текущим `ComPtr` указателем интерфейса, второй указатель интерфейса назначается току `ComPtr`.

В третьей версии указатель интерфейса присваивается току. `ComPtr`

В четвертой версии, если указатель интерфейса значения назначения не `ComPtr` совпадает с текущим указателем интерфейса, `ComPtr`второй указатель интерфейса назначается току .

Пятая версия является копировальной оператором; ссылка на `ComPtr` a присваивается текущему `ComPtr`.

Шестая версия — это копировец, который использует семантику перемещения; rvalue ссылка `ComPtr` на, если какой-либо тип статический литые, а затем назначен ы тока `ComPtr`.

Седьмая версия — это копировец, который использует семантику перемещения; rvalue ссылка `ComPtr` на тип *U* является статическим литые затем и назначены к текущему `ComPtr`.

## <a name="comptroperator"></a><a name="operator-equality"></a>ComPtr::оператор

Определение равенства двух объектов `ComPtr`.

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
Ссылка на объект `ComPtr`.

*B*<br/>
Ссылка на `ComPtr` другой объект.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор `true` дает, если объект *a* равен объекту *b;* в `false`противном случае, .

Второй и третий `true` операторы уступают, если объект *a* `nullptr`равен; в `false`противном случае, .

## <a name="comptroperator"></a><a name="operator-inequality"></a>ComPtr::оператор!

Определяет неравенство двух объектов `ComPtr`.

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
Ссылка на объект `ComPtr`.

*B*<br/>
Ссылка на `ComPtr` другой объект.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор `true` дает, если объект *a* не равен объекту *b;* в `false`противном случае, .

Второй и третий `true` операторы уступают, если объект *a* не `nullptr`равен; в `false`противном случае, .

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>ComPtr::оператор Microsoft::WRL::D::BoolType

Указывает, управляет `ComPtr` ли человек сроком службы интерфейса объекта.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если интерфейс связан с `ComPtr`этим, адрес [BoolStruct::Член](boolstruct-structure.md#member) данных участника; в `nullptr`противном случае, .

## <a name="comptrptr_"></a><a name="ptr"></a>ComPtr::ptr

Содержит указатель на интерфейс, который связан с `ComPtr`этим и управляется им.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Remarks

`ptr_`является внутренним, защищенным членом данных.

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtr::ReleaseandgetAddressof

Выпускает интерфейс, связанный с этим, `ComPtr` а затем извлекает адрес [ptr_](#ptr) члена данных, который содержит указатель на выпущенный интерфейс.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес [ptr_](#ptr) данных члена `ComPtr`этого .

## <a name="comptrreset"></a><a name="reset"></a>ComPtr::Перезагрузка

Выпускает все ссылки для указателя на интерфейс, `ComPtr`который связан с этим.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Возвращаемое значение

Число освобожденных ссылок, если таковые имеются.

## <a name="comptrswap"></a><a name="swap"></a>ComPtr::Swap

Обменивает интерфейс, управляемый `ComPtr` током, с `ComPtr`интерфейсом, управляемым указанным.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Параметры

*R*<br/>
`ComPtr`.
