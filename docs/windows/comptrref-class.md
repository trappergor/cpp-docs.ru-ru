---
title: Comptrref-класс | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3902bcb43b1aa02f6d5ec66b919a2685dccccd99
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070313"
---
# <a name="comptrref-class"></a>ComPtrRef - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Объект [ComPtr\<T >](../windows/comptr-class.md) тип или тип, производный от него, а не просто интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Примечания

Представляет ссылку на объект типа `ComPtr<T>`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef::ComPtrRef](#comptrref) | Инициализирует новый экземпляр класса `ComPtrRef` класс из заданного указателя в другой `ComPtrRef` объекта.

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::GetAddressOf](#getaddressof)                     | Извлекает адрес указателя на интерфейс, представленный текущим `ComPtrRef` объекта.
[ComPtrRef::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Удаляет текущий `ComPtrRef` и возвращает указатель на указатель на интерфейс, который был представлен `ComPtrRef` объекта.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                     | Описание
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::operator InterfaceType **](#operator-interfacetype-star-star) | Удаляет текущий `ComPtrRef` и возвращает указатель на указатель на интерфейс, который был представлен `ComPtrRef` объекта.
[ComPtrRef::operator T *](#operator-t-star)                               | Возвращает значение [ptr_](../windows/comptrrefbase-ptr-data-member.md) данными-членом текущим объектом ComPtrRef.
[ComPtrRef::operator void **](#operator-void-star-star)                   | Удаляет текущий `ComPtrRef` объекта, приведение указателя на интерфейс, который был представлен `ComPtrRef` объекта как указатель к указатель to `void`и затем возвращает указатель приведения.
[ComPtrRef::operator *](#operator-star)                                   | Извлекает указатель на интерфейс, представленный текущим `ComPtrRef` объекта.
[ComPtrRef::operator ==](#operator-equality)                              | Определение равенства двух объектов `ComPtrRef`.
[ComPtrRef::operator! =](#operator-inequality)                            | Определяет неравенство двух объектов `ComPtrRef`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="comptrref"></a>ComPtrRef::ComPtrRef

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Базовое значение другого `ComPtrRef` объекта.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `ComPtrRef` класс из заданного указателя в другой `ComPtrRef` объекта.

## <a name="getaddressof"></a>ComPtrRef::GetAddressOf

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес указателя на интерфейс, представленный текущим `ComPtrRef` объекта.

### <a name="remarks"></a>Примечания

Извлекает адрес указателя на интерфейс, представленный текущим `ComPtrRef` объекта.

## <a name="operator-equality"></a>ComPtrRef::operator ==

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
Ссылка на объект `ComPtrRef`.

*b*<br/>
Ссылка на другой `ComPtrRef` объект или указатель на анонимный тип (`void*`).

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает **true** Если объект *a* равен объекту *b*; в противном случае **false**.

Второй и третий операторы возвращают **true** Если объект *a* равен **nullptr**; в противном случае **false**.

Четвертый и пятый операторы yield **true** Если объект *a* равен объекту *b*; в противном случае **false**.

### <a name="remarks"></a>Примечания

Определение равенства двух объектов `ComPtrRef`.

## <a name="operator-inequality"></a>ComPtrRef::operator! =

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Параметры

*a*<br/>
Ссылка на объект `ComPtrRef`.

*b*<br/>
Ссылка на другой `ComPtrRef` объект или указатель на анонимный объект (`void*`).

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает **true** Если объект *a* не равен объекту *b*; в противном случае **false**.

Второй и третий операторы возвращают **true** Если объект *a* не равно **nullptr**; в противном случае **false**.

Четвертый и пятый операторы yield **true** Если объект *a* не равен объекту *b*; в противном случае **false**.

### <a name="remarks"></a>Примечания

Определяет неравенство двух объектов `ComPtrRef`.

## <a name="operator-interfacetype-star-star"></a>ComPtrRef::operator InterfaceType **

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` и возвращает указатель на указатель на интерфейс, который был представлен `ComPtrRef` объекта.

## <a name="operator-star"></a>ComPtrRef::operator *

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный текущим `ComPtrRef` объекта.

### <a name="remarks"></a>Примечания

Извлекает указатель на интерфейс, представленный текущим `ComPtrRef` объекта.

## <a name="operator-t-star"></a>ComPtrRef::operator T *

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
operator T*();
```

### <a name="remarks"></a>Примечания

Возвращает значение [ptr_](../windows/comptrrefbase-ptr-data-member.md) данными-членом текущего `ComPtrRef` объекта.

## <a name="operator-void-star-star"></a>ComPtrRef::operator void\*\*

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` объекта, приведение указателя на интерфейс, который был представлен `ComPtrRef` объекта как указатель к указатель to `void`и затем возвращает указатель приведения.

## <a name="releaseandgetaddressof"></a>ComPtrRef::ReleaseAndGetAddressOf

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который был представлен в удаленные `ComPtrRef` объекта.

### <a name="remarks"></a>Примечания

Удаляет текущий `ComPtrRef` и возвращает указатель на указатель на интерфейс, который был представлен `ComPtrRef` объекта.
