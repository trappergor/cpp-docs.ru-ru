---
title: Класс WeakReference
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
ms.openlocfilehash: a3372a176a158dd9c89eb888c8deb0244eef9a84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654939"
---
# <a name="weakreference-class"></a>Класс WeakReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakReference;
```

## <a name="remarks"></a>Примечания

Представляет *слабую ссылку* , можно использовать с помощью среды выполнения Windows или классической модели COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.

Объект `WeakReference` поддерживает *строгую ссылку*, которой является указателем на объект и *число строгую ссылку*, то есть числа копий строгую ссылку, которые были распространены, `Resolve()` метод. Несмотря на то ненулевое число строгую ссылку, строгая ссылка является действительной и объект доступен. Надежный счетчик достигает нуля, строгая ссылка является недопустимым, и объект недоступен.

Объект `WeakReference` объекта обычно используется для представления объекта, существование которого управляет внешний поток или приложение. Например, конструкция `WeakReference` объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.

`WeakReference` Методы являются потокобезопасными.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                  | Описание
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference::WeakReference](#weakreference)        | Инициализирует новый экземпляр класса `WeakReference`.
[WeakReference:: ~ WeakReference](#tilde-weakreference) | Деинициализирует (уничтожает) текущий экземпляр `WeakReference` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                                 | Описание
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::DecrementStrongReference](#decrementstrongreference) | Уменьшает текущий счетчик строгая ссылка `WeakReference` объекта.
[WeakReference::IncrementStrongReference](#incrementstrongreference) | Увеличивает счетчик строгую ссылку текущего `WeakReference` объекта.
[WeakReference::Resolve](#resolve)                                   | Устанавливает заданный указатель в текущее значение строгую ссылку, если строгую ссылку count не равно нулю.
[WeakReference::SetUnknown](#setunknown)                             | Задает строгая ссылка текущего `WeakReference` объект в заданный указатель интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WeakReference`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="tilde-weakreference"></a>WeakReference:: ~ WeakReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Деинициализирует текущий экземпляр `WeakReference` класса.

## <a name="decrementstrongreference"></a>WeakReference::DecrementStrongReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Примечания

Уменьшает текущий счетчик строгая ссылка `WeakReference` объекта.

Надежный счетчик достигает нуля, строгая ссылка имеет значение `nullptr`.

### <a name="return-value"></a>Возвращаемое значение

Счетчик уменьшается на единицу строгую ссылку.

## <a name="incrementstrongreference"></a>WeakReference::IncrementStrongReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик увеличивается строгую ссылку.

### <a name="remarks"></a>Примечания

Увеличивает счетчик строгую ссылку текущего `WeakReference` объекта.

## <a name="resolve"></a>WeakReference::Resolve

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
После завершения этой операции копию текущей строгую ссылку, если величина строгая ссылка имеет ненулевое значение.

### <a name="return-value"></a>Возвращаемое значение

- Значение S_OK, если операция выполнена успешно и строгую ссылку счетчик равен нулю. *PpvObject* параметр имеет значение `nullptr`.

- Значение S_OK, если операция выполнена успешно и строгую ссылку count не равно нулю. *PpvObject* параметру присваивается строгая ссылка.

- В противном случае — значение HRESULT, указывающее причину этой операции не удалось.

### <a name="remarks"></a>Примечания

Устанавливает заданный указатель в текущее значение строгую ссылку, если строгую ссылку count не равно нулю.

## <a name="setunknown"></a>WeakReference::SetUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Параметры

*UNK*<br/>
Указатель на `IUnknown` интерфейс для объекта.

### <a name="remarks"></a>Примечания

Задает строгая ссылка текущего `WeakReference` объект в заданный указатель интерфейса.

## <a name="weakreference"></a>WeakReference::WeakReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
WeakReference();
```

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `WeakReference`.

Указатель строгую ссылку для `WeakReference` инициализируется с `nullptr`, и число строгую ссылку устанавливается равным 1.
