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
ms.openlocfilehash: a80c0ec14da2a955a95ac84dd3975212ef20ae04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374220"
---
# <a name="weakreference-class"></a>Класс WeakReference

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
class WeakReference;
```

## <a name="remarks"></a>Remarks

Представляет *собой слабую ссылку,* которая может быть использована с Windows Runtime или классический COM. Слабая ссылка представляет собой объект, который может быть доступен или недоступен.

Объект `WeakReference` поддерживает *сильную ссылку,* которая является указателем на объект, и *сильное количество ссылок,* которое является числом копий сильной ссылки, которые были распространены `Resolve()` методом. В то время как сильное количество ссылок неявляется, сильная ссылка действительна и объект доступен. Когда сильное количество ссылок становится нулевым, сильная ссылка недействительна и объект недоступен.

Объект `WeakReference` обычно используется для представления объекта, существование которого контролируется внешним потоком или приложением. Например, построить `WeakReference` объект из ссылки на объект файла. Пока открыт файл, строгая ссылка является действительной. Но если закрыть файл, строгая ссылка станет недействительной.

Методы `WeakReference` безопасны для потоков.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                  | Описание
----------------------------------------------------- | ---------------------------------------------------------------------------
[СлабыйСправка::СлабаяСправка](#weakreference)        | Инициализирует новый экземпляр класса `WeakReference`.
[СлабыйСправка::](#tilde-weakreference) | Деприиратизирует (уничтожает) `WeakReference` текущий экземпляр класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                                 | Описание
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[СлабыйСправка::DecrementStrongСправка](#decrementstrongreference) | Декретирует сильное количество ссылок текущего `WeakReference` объекта.
[СлабыйСправка::IncrementStrongСправка](#incrementstrongreference) | Приращения сильного количества `WeakReference` ссылок текущего объекта.
[СлабыйСправка::Решение](#resolve)                                   | Устанавливает указанный указатель на текущее сильное эталонное значение, если сильное количество ссылок неявляется.
[СлабыйСправка::SetUnknown](#setunknown)                             | Устанавливает сильную ссылку `WeakReference` текущего объекта на указанный указатель интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`WeakReference`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a>СлабыйСправка::

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Remarks

Деприиратизирует текущий `WeakReference` экземпляр класса.

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a>СлабыйСправка::DecrementStrongСправка

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Remarks

Декретирует сильное количество ссылок текущего `WeakReference` объекта.

Когда сильное количество ссылок становится нулевым, сильная ссылка устанавливается на `nullptr`.

### <a name="return-value"></a>Возвращаемое значение

Decremented сильный отсчет справки.

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a>СлабыйСправка::IncrementStrongСправка

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Возвращаемое значение

Приращенный сильный отсчет ссылок.

### <a name="remarks"></a>Remarks

Приращения сильного количества `WeakReference` ссылок текущего объекта.

## <a name="weakreferenceresolve"></a><a name="resolve"></a>СлабыйСправка::Решение

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

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
Когда эта операция завершается, копия текущей сильной ссылки, если сильное количество ссылок неявляется.

### <a name="return-value"></a>Возвращаемое значение

- S_OK если эта операция успешна, а сильное количество ссылок равно нулю. Параметр *ppvObject* установлен `nullptr`на .

- S_OK если эта операция является успешной, и сильный отсчет ссылок неявляется. Параметр *ppvObject* настроен на сильную ссылку.

- В противном случае, HRESULT, который указывает причину этой операции не удалось.

### <a name="remarks"></a>Remarks

Устанавливает указанный указатель на текущее сильное эталонное значение, если сильное количество ссылок неявляется.

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a>СлабыйСправка::SetUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Параметры

*Unk*<br/>
Указатель на `IUnknown` интерфейс объекта.

### <a name="remarks"></a>Remarks

Устанавливает сильную ссылку `WeakReference` текущего объекта на указанный указатель интерфейса.

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a>СлабыйСправка::СлабаяСправка

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
WeakReference();
```

### <a name="remarks"></a>Remarks

Инициализирует новый экземпляр класса `WeakReference`.

Сильный указатель отсчета для `WeakReference` объекта `nullptr`инициализирован к, и сильное отсчет справки инициализирован до 1.
