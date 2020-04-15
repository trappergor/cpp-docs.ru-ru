---
title: Класс WeakRef
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 681f5a64c3e2902c66facbd4f0ac3a3663a7e79d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374257"
---
# <a name="weakref-class"></a>Класс WeakRef

Представляет собой *слабую ссылку* , которая может использоваться только в среде выполнения Windows, а не в классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор WeakRef::WeakRef](#weakref)|Инициализирует новый экземпляр класса `WeakRef`.|
|[Деструктор WeakRef::~WeakRef](#tilde-weakref)|Деприиратизирует текущий `WeakRef` экземпляр класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод WeakRef::As](#as)|Устанавливает указанный `ComPtr` параметр указателя для представления указанного интерфейса.|
|[Метод WeakRef::AsIID](#asiid)|Устанавливает указанный `ComPtr` параметр указателя для представления указанного идентификатора интерфейса.|
|[Метод WeakRef::CopyTo](#copyto)|Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор WeakRef::operator&](#operator-ampersand-operator)|Возвращает `ComPtrRef` объект, представляющий `WeakRef` текущий объект.|

## <a name="remarks"></a>Remarks

Объект `WeakRef` поддерживает *сильную ссылку,* которая связана с объектом, и может быть действительным или недействительным. Позвоните `As()` `AsIID()` или метод для получения сильной ссылки. Когда строгая ссылка допустима, возможно обращение к связанному объекту. Когда строгая ссылка недопустима (`nullptr`), связанный объект недоступен.

Объект `WeakRef` обычно используется для представления объекта, существование которого контролируется внешним потоком или приложением. Например, построить `WeakRef` объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.

Обратите внимание на изменение в поведении методов [As](#as), [AsIID](#asiid) и [CopyTo](#copyto) в пакете SDK для Windows 10. Ранее, после вызова любого из этих `WeakRef` методов, можно проверить, `nullptr` чтобы определить, если сильная ссылка была успешно получена, как и в следующем коде:

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

Приведенный выше код не работает при использовании пакета SDK для Windows 10 (или более поздней версии). Вместо этого, проверьте указатель, `nullptr`который был принят в для .

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

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>СлабыйРеф:::-Слабый Реф Деструктор

Деприиратизирует текущий `WeakRef` экземпляр класса.

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>СлабыйРеф::Как метод

Устанавливает указанный `ComPtr` параметр указателя для представления указанного интерфейса.

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

*U*<br/>
Идентификатор интерфейса.

*Ptr*<br/>
Когда эта операция завершается, объект, представляющий параметр *U.*

### <a name="return-value"></a>Возвращаемое значение

- S_OK, если эта операция увенчается успехом; в противном случае, HRESULT, который указывает причину `nullptr`операции не удалось, и *ptr* установлен на .

- S_OK если эта операция выполнена, но текущий `WeakRef` объект уже освобожден. Параметр *ptr* `nullptr`установлен на .

- S_OK если эта операция удается, но текущий `WeakRef` объект не вытекает из параметра *U*. Параметр *ptr* `nullptr`установлен на .

### <a name="remarks"></a>Remarks

Ошибка испускается, если параметр *U* является `IWeakReference`или `IInspectable`не получен из.

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

Начиная с Windows 10 SDK, этот `WeakRef` метод `nullptr` не устанавливает экземпляр, если слабая ссылка не может быть `WeakRef` получена, так что вы должны избегать проверки ошибок код, который проверяет для `nullptr`. Вместо этого, проверьте *ptr* для `nullptr`.

## <a name="weakrefasiid-method"></a><a name="asiid"></a>WeakRef::Метод ASIID

Устанавливает указанный `ComPtr` параметр указателя для представления указанного идентификатора интерфейса.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*Ptr*<br/>
Когда эта операция завершается, объект, представляющий параметр *riid.*

### <a name="return-value"></a>Возвращаемое значение

- S_OK, если эта операция увенчается успехом; в противном случае, HRESULT, который указывает причину `nullptr`операции не удалось, и *ptr* установлен на .

- S_OK если эта операция выполнена, но текущий `WeakRef` объект уже освобожден. Параметр *ptr* `nullptr`установлен на .

- S_OK если эта операция удается, но текущий `WeakRef` объект не вытекает из параметра *riid*. Параметр *ptr* `nullptr`установлен на . (Дополнительные сведения см. в разделе "Примечания".)

### <a name="remarks"></a>Remarks

Ошибка испускается, если параметр *riid* `IInspectable`не получен из . Эта ошибка заменяет возвращаемое значение.

Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон (не показанный здесь, но объявленный в файле заголовка) является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../../cpp/auto-cpp.md) .

Начиная с Windows 10 SDK, этот `WeakRef` метод `nullptr` не устанавливает экземпляр, если слабая ссылка не может быть `WeakRef` получена, так что вы должны избегать проверки ошибок код, который проверяет для `nullptr`. Вместо этого, проверьте *ptr* для `nullptr`.

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>WeakRef::CopyTo Метод

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

*U*<br/>
Указатель `IInspectable` интерфейса. Ошибка испускается, если *U* не `IInspectable`получен от .

*riid*<br/>
Идентификатор интерфейса. Ошибка испускается, если *риид* не `IWeakReference`получен из .

*Ptr*<br/>
Вдвойне-косвенный указатель `IInspectable` на `IWeakReference`или .

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Для получения дополнительной информации, **см.**

### <a name="remarks"></a>Remarks

Возвращаемое значение S_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если S_OK возвращен, проверьте, что параметр *p* является сильной ссылкой; то есть параметр *p* не `nullptr`равен .

Начиная с Windows 10 SDK, этот `WeakRef` метод `nullptr` не устанавливает экземпляр, если слабая ссылка не может быть `WeakRef` `nullptr`получена, так что вы должны избегать проверки ошибок код, который проверяет для . Вместо этого, проверьте *ptr* для `nullptr`.

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>WeakRef:Оператор&amp;

Возвращает `ComPtrRef` объект, представляющий `WeakRef` текущий объект.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `ComPtrRef` представляющий `WeakRef` текущий объект.

### <a name="remarks"></a>Remarks

Это внутренний оператор-помощник, который не предназначен для использования в вашем коде.

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>СлабыйРеф::Слабый Конструктор

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

*Ptr*<br/>
Указатель, ссылка или rvalue-ссылка на существующий объект, который инициирует текущий `WeakRef` объект.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует пустой `WeakRef` объект. Второй конструктор инициализирует `WeakRef` объект от `IWeakReference` указателя до интерфейса. Третий конструктор инициализирует `WeakRef` объект `ComPtr<IWeakReference>` из ссылки на объект. Четвертый и пятый конструкторы `WeakRef` инициализируют объект с другого `WeakRef` объекта.
