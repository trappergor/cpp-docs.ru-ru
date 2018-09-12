---
title: Класс WeakRef | Документация Майкрософт
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f9b121b75e31fdd79313e36b9e1e19c1cf3200e
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691540"
---
# <a name="weakref-class"></a>Класс WeakRef

Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakRef : public ComPtr<IWeakReference>
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор WeakRef::WeakRef](#weakref)|Инициализирует новый экземпляр класса `WeakRef`.|
|[Деструктор WeakRef::~WeakRef](#tilde-weakref)|Деинициализирует текущий экземпляр `WeakRef` класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод WeakRef::As](#as)|Задает указанный `ComPtr` параметр-указатель для представления указанного интерфейса.|
|[Метод WeakRef::AsIID](#asiid)|Задает указанный `ComPtr` параметр-указатель для представления идентификатора указанного интерфейса.|
|[Метод WeakRef::CopyTo](#copyto)|Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор WeakRef::operator&](#operator-ampersand-operator)|Возвращает `ComPtrRef` , представляющий текущий `WeakRef` объекта.|

## <a name="remarks"></a>Примечания

Объект `WeakRef` поддерживает *строгую ссылку*, которая связана с объектом и может быть допустимой или недопустимой. Вызовите `As()` или `AsIID()` метод, чтобы получить строгую ссылку. Когда строгая ссылка допустима, возможно обращение к связанному объекту. Когда строгая ссылка недопустима (`nullptr`), связанный объект недоступен.

Объект `WeakRef` объекта обычно используется для представления объекта, существование которого управляет внешний поток или приложение. Например, конструкция `WeakRef` объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.

Обратите внимание, что изменение в поведении [как](#as), [AsIID](#asiid) и [CopyTo](#copyto) методы пакета SDK для Windows 10. Ранее после вызова любого из этих методов, можно проверить `WeakRef` для `nullptr` для определения того, если строгую ссылку был успешно получен, как показано в следующем коде:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)  
{
    wprintf(L"Couldn’t get strong ref!");
}
```

Приведенный выше код не работает при использовании пакета SDK для Windows 10 (или более поздней версии). Вместо этого проверьте указатель, который был передан в для `nullptr`.

```cpp
if (strongRef == nullptr)  
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

`WeakRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="tilde-weakref"></a>WeakRef:: ~ WeakRef деструктор

Деинициализирует текущий экземпляр `WeakRef` класса.

```cpp
~WeakRef();
```

## <a name="as"></a>Метод WeakRef::As

Задает указанный `ComPtr` параметр-указатель для представления указанного интерфейса.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>Параметры

*U*  
Идентификатор интерфейса.

*ptr*  
После завершения операции, объект, представляющий параметр *U*.

### <a name="return-value"></a>Возвращаемое значение

- Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину произошел сбой операции, и *ptr* присваивается `nullptr`.

- Значение S_OK, если операция завершилась успешно, но текущий `WeakRef` объект уже был выпущен. Параметр *ptr* присваивается `nullptr`.

- Значение S_OK, если операция завершилась успешно, но текущий `WeakRef` объект не является производным от параметра *U*. Параметр *ptr* присваивается `nullptr`.

### <a name="remarks"></a>Примечания

Ошибка создается в том случае, если параметр *U* — `IWeakReference`, или не является производным от `IInspectable`.

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .

Начиная с пакета SDK для Windows 10, этот метод устанавливает `WeakRef` экземпляр `nullptr` Если не удалось получить слабую ссылку, поэтому следует избегать кода проверки ошибок, которое проверяет `WeakRef` для `nullptr`. Вместо этого проверьте *ptr* для `nullptr`.

## <a name="asiid"></a>Метод WeakRef::AsIID

Задает указанный `ComPtr` параметр-указатель для представления идентификатора указанного интерфейса.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Параметры

*riid*  
Идентификатор интерфейса.

*ptr*  
После завершения операции, объект, представляющий параметр *riid*.

### <a name="return-value"></a>Возвращаемое значение

- Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину произошел сбой операции, и *ptr* присваивается `nullptr`.

- Значение S_OK, если операция завершилась успешно, но текущий `WeakRef` объект уже был выпущен. Параметр *ptr* присваивается `nullptr`.

- Значение S_OK, если операция завершилась успешно, но текущий `WeakRef` объект не является производным от параметра *riid*. Параметр *ptr* присваивается `nullptr`. (Дополнительные сведения см. в разделе "Примечания".)

### <a name="remarks"></a>Примечания

Ошибка создается в том случае, если параметр *riid* не является производным от `IInspectable`. Эта ошибка заменяет возвращаемое значение.

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон (не показанный здесь, но объявленный в файле заголовка) является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .

Начиная с пакета SDK для Windows 10, этот метод устанавливает `WeakRef` экземпляр `nullptr` Если не удалось получить слабую ссылку, поэтому следует избегать кода проверки ошибок, которое проверяет `WeakRef` для `nullptr`. Вместо этого проверьте *ptr* для `nullptr`.

## <a name="copyto"></a>Метод WeakRef::CopyTo

Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Параметры

*U*  
Указатель `IInspectable` интерфейс. Если возникает ошибка *U* не является производным от `IInspectable`.

*riid*  
Идентификатор интерфейса. Если возникает ошибка *riid* не является производным от `IWeakReference`.

*ptr*  
Двойной косвенный указатель на `IInspectable` или `IWeakReference`.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Дополнительные сведения см. в разделе **Замечания**.

### <a name="remarks"></a>Примечания

Возвращаемое значение S_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если возвращается значение S_OK, протестируйте этот параметр *p* строгую ссылку, то есть параметр *p* не соответствует `nullptr`.

Начиная с пакета SDK для Windows 10, этот метод устанавливает `WeakRef` экземпляр `nullptr` Если не удалось получить слабую ссылку, поэтому следует избегать произошла ошибка при проверке кода, который проверяет `WeakRef` для `nullptr`. Вместо этого проверьте *ptr* для `nullptr`.

## <a name="operator-ampersand-operator"></a>Оператор WeakRef::operator&amp; оператор

Возвращает `ComPtrRef` , представляющий текущий `WeakRef` объекта.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()  
```

### <a name="return-value"></a>Возвращаемое значение

Объект `ComPtrRef` , представляющий текущий `WeakRef` объекта.

### <a name="remarks"></a>Примечания

Это внутренний вспомогательный оператор, который не предназначен для использования в коде.

## <a name="weakref"></a>Конструктор WeakRef::WeakRef

Инициализирует новый экземпляр класса `WeakRef`.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)  
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>Параметры

*ptr*  
Указатель, ссылка или rvalue ссылка на существующий объект, который инициализирует текущий `WeakRef` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует пустой `WeakRef` объекта. Второй конструктор инициализирует `WeakRef` объекта из указателя на `IWeakReference` интерфейс. Третий конструктор инициализирует `WeakRef` объект из ссылки на `ComPtr<IWeakReference>` объекта. Инициализирует четвертый и пятый конструкторы `WeakRef` из другого объекта `WeakRef` объекта.
