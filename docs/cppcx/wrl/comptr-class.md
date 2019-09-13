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
ms.openlocfilehash: 1e20a991c8f32027aeea6a17df0534aa6e1c2c43
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498416"
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
Класс, к которому текущий `ComPtr` объект является дружественным. (Шаблон, который использует этот параметр, защищен.)

## <a name="remarks"></a>Примечания

`ComPtr<>`объявляет тип, представляющий указатель базового интерфейса. Используйте `ComPtr<>` для объявления переменной, а затем используйте оператор доступа к членам стрелки ()`->`для доступа к функции-члену интерфейса.

Дополнительные сведения о смарт-указателях см. в подразделе "интеллектуальные указатели COM" статьи [рекомендации по кодированию com](/windows/win32/LearnWin32/com-coding-practices) в библиотеке MSDN.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name            | Описание
--------------- | ---------------------------------------------------------------
`InterfaceType` | Синоним для типа, указанного параметром-шаблоном *T* .

### <a name="public-constructors"></a>Открытые конструкторы

name                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:: ComPtr](#comptr)        | Инициализирует новый экземпляр класса `ComPtr`. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.
[ComPtr:: ~ ComPtr](#tilde-comptr) | Выполняет деинициализацию экземпляра `ComPtr`.

### <a name="public-methods"></a>Открытые методы

name                                                      | Описание
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr:: AS](#as)                                         | `ComPtr` Возвращает объект, представляющий интерфейс, определяемый указанным параметром шаблона.
[ComPtr:: AsIID](#asiid)                                   | `ComPtr` Возвращает объект, представляющий интерфейс, определяемый указанным идентификатором интерфейса.
[ComPtr:: AsWeak](#asweak)                                 | Извлекает слабую ссылку на текущий объект.
[ComPtr:: Attach](#attach)                                 | Связывает это `ComPtr` с типом интерфейса, указанным в параметре типа текущего шаблона.
[ComPtr:: CopyTo](#copyto)                                 | Копирует текущий или указанный интерфейс, связанный с этим `ComPtr` параметром, в указанный указатель на выход.
[ComPtr::D етач](#detach)                                 | Отменяет связь `ComPtr` этого интерфейса с интерфейсом, который он представляет.
[ComPtr:: Get](#get)                                       | Получает указатель на интерфейс, связанный с данным `ComPtr`.
[ComPtr:: GetAddressOf](#getaddressof)                     | Извлекает адрес элемента данных [ptr_](#ptr) , который содержит указатель на интерфейс, представленный этим `ComPtr`объектом.
[ComPtr:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | Освобождает интерфейс, связанный с этим `ComPtr` , а затем извлекает адрес элемента данных [ptr_](#ptr) , который содержит указатель на освобожденный интерфейс.
[ComPtr::Reset](#reset)                                   | Освобождает все ссылки на интерфейс, связанный с этим `ComPtr`указателем.
[ComPtr:: swap](#swap)                                     | Обменивается данными интерфейсом, управляемым `ComPtr` текущим объектом, с интерфейсом, `ComPtr`управляемым указанным.

### <a name="protected-methods"></a>Защищенные методы

name                                        | Описание
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr:: InternalAddRef](#internaladdref)   | Увеличивает значение счетчика ссылок для интерфейса, связанного с этим `ComPtr`.
[ComPtr:: InternalRelease](#internalrelease) | Выполняет операцию освобождения COM для интерфейса, связанного с этим `ComPtr`.

### <a name="public-operators"></a>Открытые операторы

name                                                                                           | Описание
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr:: operator &](#operator-ampersand)                                                       | Извлекает адрес текущего `ComPtr`объекта.
[ComPtr:: operator — >](#operator-arrow)                                                          | Извлекает указатель на тип, заданный текущим параметром шаблона.
[ComPtr:: operator =](#operator-assign)                                                          | Присваивает значение текущему `ComPtr`.
[ComPtr:: operator = =](#operator-equality)                                                       | Определение равенства двух объектов `ComPtr`.
[ComPtr:: operator! =](#operator-inequality)                                                     | Определяет неравенство двух объектов `ComPtr`.
[ComPtr:: operator Microsoft:: WRL::D состояния:: BoolType](#operator-microsoft-wrl-details-booltype) | Указывает, управляет ли `ComPtr` объект временем существования объекта интерфейсом.

### <a name="protected-data-members"></a>Защищенные члены данных

name                 | Описание
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::p tr_](#ptr) | Содержит указатель на интерфейс, связанный с, и управляется этим `ComPtr`объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft:: WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

Выполняет деинициализацию экземпляра `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr:: AS

`ComPtr` Возвращает объект, представляющий интерфейс, определяемый указанным параметром шаблона.

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
Интерфейс, представляемый параметром *p*.

*p*<br/>
Объект, представляющий интерфейс, указанный параметром *U.* `ComPtr` Параметр *p* не должен ссылаться на текущий `ComPtr` объект.

### <a name="remarks"></a>Примечания

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="asiid"></a>ComPtr:: AsIID

`ComPtr` Возвращает объект, представляющий интерфейс, определяемый указанным идентификатором интерфейса.

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
Если у объекта есть интерфейс, идентификатор которого равен *riid*, то непрямой указатель на интерфейс, указанный параметром *riid* ; в противном случае — `IUnknown`указатель на.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="asweak"></a>ComPtr:: AsWeak

Извлекает слабую ссылку на текущий объект.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Параметры

*пвеакреф*<br/>
После завершения операции представляет указатель на объект слабой ссылки.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="attach"></a>ComPtr:: Attach

Связывает это `ComPtr` с типом интерфейса, указанным в параметре типа текущего шаблона.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Параметры

*other*<br/>
Тип интерфейса.

## <a name="comptr"></a>ComPtr:: ComPtr

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

*other*<br/>
Объект типа *U*.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Первый конструктор является конструктором по умолчанию, который явно создает пустой объект. Второй конструктор указывает [__nullptr](../../extensions/nullptr-cpp-component-extensions.md), который явно создает пустой объект.

Третий конструктор создает объект из объекта, заданного указателем. ComPtr теперь владеет ссылкой на память и поддерживает для нее счетчик ссылок.

Четвертый и пятый конструкторы являются конструкторами копий. Пятый конструктор копирует объект, если он преобразуется в текущий тип.

Шестой и седьмой конструкторы являются конструкторами перемещения. Седьмой конструктор перемещает объект, если он преобразуется в текущий тип.

## <a name="copyto"></a>ComPtr:: CopyTo

Копирует текущий или указанный интерфейс, связанный с этим `ComPtr` параметром, в указанный указатель.

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

Значение S_OK в случае успешного выполнения; в противном случае возвращается значение HRESULT, указывающее `QueryInterface` , почему не удалось выполнить неявную операцию.

### <a name="remarks"></a>Примечания

Первая функция возвращает копию указателя на интерфейс, связанный с этим `ComPtr`. Эта функция всегда возвращает значение S_OK.

Вторая функция выполняет `QueryInterface` операцию с интерфейсом, связанным с данным `ComPtr` интерфейсом, для интерфейса, указанного параметром *riid* .

Третья функция выполняет `QueryInterface` операцию с интерфейсом, связанным с этим `ComPtr` , для базового интерфейса параметра *U* .

## <a name="detach"></a>ComPtr::D етач

Отменяет связь этого объекта `ComPtr` с интерфейсом, который он представляет.

```cpp
T* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который был представлен этим объектом `ComPtr`.

## <a name="get"></a>ComPtr:: Get

Получает указатель на интерфейс, связанный с данным `ComPtr`.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, связанный с этим `ComPtr`.

## <a name="getaddressof"></a>ComPtr:: GetAddressOf

Извлекает адрес элемента данных [ptr_](#ptr) , который содержит указатель на интерфейс, представленный этим `ComPtr`объектом.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес переменной.

## <a name="internaladdref"></a>ComPtr:: InternalAddRef

Увеличивает значение счетчика ссылок для интерфейса, связанного с этим `ComPtr`.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Примечания

Этот метод защищен.

## <a name="internalrelease"></a>ComPtr:: InternalRelease

Выполняет операцию освобождения COM для интерфейса, связанного с этим `ComPtr`.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Примечания

Этот метод защищен.

## <a name="operator-ampersand"></a>ComPtr:: operator&amp;

Освобождает интерфейс, связанный с этим объектом `ComPtr`, а затем извлекает адрес объекта `ComPtr`.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Возвращаемое значение

Слабая ссылка на текущий объект `ComPtr`.

### <a name="remarks"></a>Примечания

Этот метод отличается от [ComPtr:: GetAddressOf](#getaddressof) тем, что этот метод освобождает ссылку на указатель интерфейса. Используйте метод `ComPtr::GetAddressOf`, если необходим адрес указателя интерфейса, но этот интерфейс освобождать не требуется.

## <a name="operator-arrow"></a>ComPtr:: operator —&gt;

Извлекает указатель на тип, заданный текущим параметром шаблона.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на тип, заданный текущим именем типа шаблона.

### <a name="remarks"></a>Примечания

Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция создает `IUnknown` типы `private` , `virtual`а не.

## <a name="operator-assign"></a>ComPtr:: operator =

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
Ссылка на указатель, ссылку или rvalue на тип или на другой `ComPtr`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий `ComPtr`объект.

### <a name="remarks"></a>Примечания

Первая версия этого оператора присваивает пустое значение текущему `ComPtr`значению.

Во второй версии, если указатель интерфейса назначения не совпадает с текущим `ComPtr` указателем интерфейса, второй указатель интерфейса назначается текущему. `ComPtr`

В третьей версии указатель на присвоенный интерфейс назначается текущему `ComPtr`.

В четвертой версии, если указатель интерфейса назначенного значения не совпадает с текущим `ComPtr` указателем интерфейса, второй указатель интерфейса назначается текущему. `ComPtr`

Пятая версия является оператором копирования; Ссылка на объект `ComPtr` присваивается текущему `ComPtr`элементу.

Шестая версия — это оператор Copy, использующий семантику перемещения; Ссылка rvalue на, `ComPtr` если какой-либо тип является статическим приведением, а затем назначается текущему. `ComPtr`

Седьмая версия — это оператор Copy, использующий семантику перемещения; Ссылка rvalue на `ComPtr` тип *U* является статической приведением и присваивается текущему `ComPtr`.

## <a name="operator-equality"></a>ComPtr:: operator = =

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
Ссылка на другой `ComPtr` объект.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает `true` Если объект *a* равен объекту *b*; в противном случае `false`.

Второй и третий операторы возвращают `true` Если объект *a* равен `nullptr`; в противном случае `false`.

## <a name="operator-inequality"></a>ComPtr:: operator! =

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
Ссылка на другой `ComPtr` объект.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает `true` Если объект *a* не равен объекту *b*; в противном случае `false`.

Второй и третий операторы возвращают `true` Если объект *a* не равно `nullptr`; в противном случае `false`.

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr:: operator Microsoft:: WRL::D состояния:: BoolType

Указывает, управляет ли `ComPtr` объект временем существования объекта интерфейсом.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если интерфейс связан с этим `ComPtr`, то адрес `nullptr`элемента данных [BoolStruct:: Member](boolstruct-structure.md#member) ; в противном случае — значение.

## <a name="ptr"></a>ComPtr::p tr_

Содержит указатель на интерфейс, связанный с, и управляется этим `ComPtr`объектом.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Примечания

`ptr_`— Это внутренний, защищенный элемент данных.

## <a name="releaseandgetaddressof"></a>ComPtr:: ReleaseAndGetAddressOf

Освобождает интерфейс, связанный с этим `ComPtr` , а затем извлекает адрес элемента данных [ptr_](#ptr) , который содержит указатель на освобожденный интерфейс.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес элемента данных [ptr_](#ptr) этого `ComPtr`объекта.

## <a name="reset"></a>ComPtr:: Reset

Освобождает все ссылки на интерфейс, связанный с этим `ComPtr`указателем.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Возвращаемое значение

Число освобожденных ссылок, если таковые имеются.

## <a name="swap"></a>ComPtr:: swap

Обменивается данными интерфейсом, управляемым `ComPtr` текущим объектом, с интерфейсом, `ComPtr`управляемым указанным.

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

