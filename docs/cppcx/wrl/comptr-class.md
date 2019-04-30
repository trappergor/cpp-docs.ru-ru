---
title: Класс ComPtr
ms.date: 10/01/2018
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
ms.openlocfilehash: 9e5b2419f070ead17e72b1642f510f74bad8260e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398684"
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
Интерфейс, `ComPtr` представляет.

*U*<br/>
Класс, к которому текущий `ComPtr` является дружественной. (Шаблон, который использует этот параметр, защищен.)

## <a name="remarks"></a>Примечания

`ComPtr<>` Объявляет тип, представляющий указателя базового интерфейса. Используйте `ComPtr<>` объявления переменной, а затем использовать оператор доступа к членам в виде стрелки (`->`) для доступа к функция-член интерфейса.

Дополнительные сведения об интеллектуальных указателях см. подраздел «Интеллектуальные указатели COM» [COM Coding Practices](/windows/desktop/LearnWin32/com-coding-practices) раздела в библиотеке MSDN.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name            | Описание
--------------- | ---------------------------------------------------------------
`InterfaceType` | Синоним для типа, заданного параметром *T* параметр шаблона.

### <a name="public-constructors"></a>Открытые конструкторы

name                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr::ComPtr](#comptr)        | Инициализирует новый экземпляр класса `ComPtr`. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Отменяет инициализацию экземпляра `ComPtr`.

### <a name="public-methods"></a>Открытые методы

name                                                      | Описание
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | Возвращает `ComPtr` , представляющий интерфейс, определенный параметром указанного шаблона.
[ComPtr::AsIID](#asiid)                                   | Возвращает `ComPtr` , представляющий интерфейс, определенный с помощью идентификатора указанного интерфейса.
[ComPtr::AsWeak](#asweak)                                 | Извлекает слабую ссылку на текущий объект.
[ComPtr::Attach](#attach)                                 | Это связывает `ComPtr` с типом интерфейса, указанным текущим параметром типа шаблона.
[ComPtr::CopyTo](#copyto)                                 | Копирует текущий или указанный интерфейс, связанный с данным `ComPtr` в заданный выходной указатель.
[ComPtr::Detach](#detach)                                 | Отменяет связь этого `ComPtr` с интерфейсом, который он представляет.
[ComPtr::Get](#get)                                       | Извлекает указатель на интерфейс, который связан с данным `ComPtr`.
[ComPtr::GetAddressOf](#getaddressof)                     | Извлекает адрес [ptr_](#ptr) элемент данных, который содержит указатель на интерфейс, представленный этим `ComPtr`.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Освобождает интерфейс, связанный с данным `ComPtr` , а затем извлекает адрес [ptr_](#ptr) элемент данных, который содержит указатель на интерфейс, который был выпущен.
[ComPtr::Reset](#reset)                                   | Освобождает все ссылки на указатель на интерфейс, который связан с данным `ComPtr`.
[ComPtr::Swap](#swap)                                     | Меняет местами интерфейс, управляемый текущим `ComPtr` с помощью интерфейса, управляемого с помощью указанного `ComPtr`.

### <a name="protected-methods"></a>Защищенные методы

name                                        | Описание
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr::InternalAddRef](#internaladdref)   | Увеличивает счетчик ссылок интерфейса, связанного с данным `ComPtr`.
[ComPtr::InternalRelease](#internalrelease) | Выполняет операцию освобождения модели COM в интерфейсе, связанном с этим `ComPtr`.

### <a name="public-operators"></a>Открытые операторы

name                                                                                           | Описание
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[Оператор ComPtr::operator &](#operator-ampersand)                                                       | Извлекает адрес текущего `ComPtr`.
[Оператор ComPtr::operator ->](#operator-arrow)                                                          | Извлекает указатель на тип, заданный текущим параметром шаблона.
[Оператор ComPtr::operator =](#operator-assign)                                                          | Присваивает значение текущему `ComPtr`.
[Оператор ComPtr::operator ==](#operator-equality)                                                       | Определение равенства двух объектов `ComPtr`.
[Оператор ComPtr::operator! =](#operator-inequality)                                                     | Определяет неравенство двух объектов `ComPtr`.
[Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](#operator-microsoft-wrl-details-booltype) | Указывает ли `ComPtr` управление временем существования объектов интерфейса.

### <a name="protected-data-members"></a>Защищенные члены данных

name                 | Описание
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | Содержит указатель на интерфейс, который связан с и управляемые этим экземпляром `ComPtr`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Отменяет инициализацию экземпляра `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr::As

Возвращает `ComPtr` , представляющий интерфейс, определенный параметром указанного шаблона.

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
Интерфейс для представления параметром *p*.

*p*<br/>
Объект `ComPtr` объект, представляющий интерфейс, заданный параметром *U*. Параметр *p* не должен ссылаться на текущий `ComPtr` объекта.

### <a name="remarks"></a>Примечания

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="asiid"></a>ComPtr::AsIID

Возвращает `ComPtr` , представляющий интерфейс, определенный с помощью идентификатора указанного интерфейса.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*p*<br/>
Если объект имеет интерфейс, идентификатор которой равняется *riid*, двойной косвенный указатель на интерфейс, определенный следующим *riid* параметра; в противном случае указатель на `IUnknown`.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="asweak"></a>ComPtr::AsWeak

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

## <a name="attach"></a>ComPtr::Attach

Это связывает `ComPtr` с типом интерфейса, указанным текущим параметром типа шаблона.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Параметры

*other*<br/>
Тип интерфейса.

## <a name="comptr"></a>ComPtr::ComPtr

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
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>Параметры

*U*<br/>
Тип *других* параметра.

*other*<br/>
Объект типа *U*.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Первый конструктор является конструктором по умолчанию, который неявно создает пустой объект. Второй конструктор определяет [__nullptr](../../extensions/nullptr-cpp-component-extensions.md), который явно создает пустой объект.

Третий конструктор создает объект из объекта, указанного с помощью указателя.

Четвертый и пятый конструкторы являются конструкторами копий. Пятый конструктор копирует объект, если оно преобразуется в текущий тип.

Шестой и седьмой конструкторы являются конструкторы перемещения. Седьмой конструктор перемещает объект, если оно преобразуется в текущий тип.

## <a name="copyto"></a>ComPtr::CopyTo

Копирует текущий или указанный интерфейс, связанный с данным `ComPtr` в заданный указатель.

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

*ptr*<br/>
После завершения операции представляет указатель на запрошенный интерфейс.

*riid*<br/>
Идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, указывающее, почему неявный `QueryInterface` не удалось выполнить операцию.

### <a name="remarks"></a>Примечания

Первая функция возвращает копию указателя на интерфейс, связанный с данным `ComPtr`. Эта функция всегда возвращает значение S_OK.

Вторая функция выполняет `QueryInterface` операции в интерфейсе, связанном с этим `ComPtr` для интерфейса, заданного параметром *riid* параметра.

Третья функция выполняет `QueryInterface` операции в интерфейсе, связанном с этим `ComPtr` для базового интерфейса параметра *U* параметра.

## <a name="detach"></a>ComPtr::Detach

Отменяет связь этого объекта `ComPtr` с интерфейсом, который он представляет.

```cpp
T* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который был представлен этим объектом `ComPtr`.

## <a name="get"></a>ComPtr::Get

Извлекает указатель на интерфейс, который связан с данным `ComPtr`.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, связанный с данным `ComPtr`.

## <a name="getaddressof"></a>ComPtr::GetAddressOf

Извлекает адрес [ptr_](#ptr) элемент данных, который содержит указатель на интерфейс, представленный этим `ComPtr`.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес переменной.

## <a name="internaladdref"></a>ComPtr::InternalAddRef

Увеличивает счетчик ссылок интерфейса, связанного с данным `ComPtr`.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Примечания

Этот метод защищен.

## <a name="internalrelease"></a>ComPtr::InternalRelease

Выполняет операцию освобождения модели COM в интерфейсе, связанном с этим `ComPtr`.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Примечания

Этот метод защищен.

## <a name="operator-ampersand"></a>Оператор ComPtr::operator&amp;

Освобождает интерфейс, связанный с этим объектом `ComPtr`, а затем извлекает адрес объекта `ComPtr`.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Возвращаемое значение

Слабая ссылка на текущий объект `ComPtr`.

### <a name="remarks"></a>Примечания

Этот метод отличается от [ComPtr::GetAddressOf](#getaddressof) в том, что данный метод освобождает ссылку на указатель интерфейса. Используйте метод `ComPtr::GetAddressOf`, если необходим адрес указателя интерфейса, но этот интерфейс освобождать не требуется.

## <a name="operator-arrow"></a>Оператор ComPtr::operator-&gt;

Извлекает указатель на тип, заданный текущим параметром шаблона.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на тип, заданный текущим именем типа шаблона.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция делает `IUnknown` типы `private` вместо `virtual`.

## <a name="operator-assign"></a>Оператор ComPtr::operator =

Присваивает значение текущему `ComPtr`.

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

*other*<br/>
Указатель, ссылку или ссылку rvalue на тип или другой `ComPtr`.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на текущий `ComPtr`.

### <a name="remarks"></a>Примечания

Первая версия этого оператора присваивает пустое значение текущему `ComPtr`.

Во второй версии, если присваиваемый указатель интерфейса не совпадает с текущим `ComPtr` указатель на интерфейс, второй указатель интерфейса присваивается текущему `ComPtr`.

В третьей версии присваиваемый указатель интерфейса присваивается текущему `ComPtr`.

В четвертой версии, если указатель интерфейса присваиваемого значения не совпадает с текущим `ComPtr` указатель на интерфейс, второй указатель интерфейса присваивается текущему `ComPtr`.

Пятая версия является оператором копирования; ссылку на `ComPtr` назначается текущему `ComPtr`.

Шестая версия является оператором копирования, использующим перемещение семантику; ссылка rvalue на `ComPtr` Если любой тип приводится статически, а затем присваивается текущий `ComPtr`.

Седьмая версия является оператором копирования, использующим перемещение семантику; ссылка rvalue на `ComPtr` типа *U* является статическим затем приведение и назначена текущему `ComPtr`.

## <a name="operator-equality"></a>Оператор ComPtr::operator ==

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

*b*<br/>
Ссылка на другой `ComPtr` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает `true` Если объект *a* равен объекту *b*; в противном случае `false`.

Второй и третий операторы возвращают `true` Если объект *a* равен `nullptr`; в противном случае `false`.

## <a name="operator-inequality"></a>Оператор ComPtr::operator! =

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

*b*<br/>
Ссылка на другой `ComPtr` объекта.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает `true` Если объект *a* не равен объекту *b*; в противном случае `false`.

Второй и третий операторы возвращают `true` Если объект *a* не равно `nullptr`; в противном случае `false`.

## <a name="operator-microsoft-wrl-details-booltype"></a>Оператор ComPtr::operator Microsoft::WRL::Details::BoolType

Указывает ли `ComPtr` управление временем существования объектов интерфейса.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если интерфейс связан с данным `ComPtr`, адрес [BoolStruct::Member](boolstruct-structure.md#member) данные-член; в противном случае `nullptr`.

## <a name="ptr"></a>ComPtr::ptr_

Содержит указатель на интерфейс, который связан с и управляемые этим экземпляром `ComPtr`.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Примечания

`ptr_` является членом внутреннего, защищенных данных.

## <a name="releaseandgetaddressof"></a>ComPtr::ReleaseAndGetAddressOf

Освобождает интерфейс, связанный с данным `ComPtr` , а затем извлекает адрес [ptr_](#ptr) элемент данных, который содержит указатель на интерфейс, который был выпущен.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес [ptr_](#ptr) данных элементом коллекции `ComPtr`.

## <a name="reset"></a>ComPtr::Reset

Освобождает все ссылки на указатель на интерфейс, который связан с данным `ComPtr`.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Возвращаемое значение

Число освобожденных ссылок, если таковые имеются.

## <a name="swap"></a>ComPtr::Swap

Меняет местами интерфейс, управляемый текущим `ComPtr` с помощью интерфейса, управляемого с помощью указанного `ComPtr`.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Параметры

*r*<br/>
Объект `ComPtr`.

