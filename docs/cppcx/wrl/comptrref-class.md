---
title: ComPtrRef - класс
ms.date: 10/03/2018
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
ms.openlocfilehash: df9ded817227547493c04035e0abc3d948e24495
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372625"
---
# <a name="comptrref-class"></a>ComPtrRef - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
[ComPtr\<T>](comptr-class.md) тип или тип, полученный из него, а не только интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Remarks

Представляет собой ссылку на `ComPtr<T>`объект типа.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                               | Описание
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[ComPtrRef:ComPtrRef](#comptrref) | Инициализирует новый экземпляр `ComPtrRef` класса от `ComPtrRef` указанного указателя к другому объекту.

### <a name="public-methods"></a>Открытые методы

Имя                                                         | Описание
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef:GetAddressOf](#getaddressof)                     | Извлекает адрес указателя на интерфейс, представленный `ComPtrRef` текущим объектом.
[ComPtrRef::ReleaseandgetAddressof](#releaseandgetaddressof) | Удаляет текущий `ComPtrRef` объект и возвращает указатель в указатель на интерфейс, представленный `ComPtrRef` объектом.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                     | Описание
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtrRef::оператор ИнтерфейсТип](#operator-interfacetype-star-star) | Удаляет текущий `ComPtrRef` объект и возвращает указатель в указатель на интерфейс, представленный `ComPtrRef` объектом.
[ComPtrRef::оператор ТЗ](#operator-t-star)                               | Возвращает значение [ptr_](comptrrefbase-class.md#ptr) члена данных текущего объекта ComPtrRef.
[ComPtrRef::оператор пустота](#operator-void-star-star)                   | Удаляет текущий `ComPtrRef` объект, отбрасывает указатель на интерфейс, который `ComPtrRef` был представлен объектом в качестве `void`указателя на указатель к указателю, а затем возвращает указатель.
[ComPtrRef:оператор](#operator-star)                                   | Извлекает указатель на интерфейс, представленный `ComPtrRef` текущим объектом.
[ComPtrRef::оператор](#operator-equality)                              | Определение равенства двух объектов `ComPtrRef`.
[ComPtrRef::оператор!](#operator-inequality)                            | Определяет неравенство двух объектов `ComPtrRef`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="comptrrefcomptrref"></a><a name="comptrref"></a>ComPtrRef:ComPtrRef

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*Ptr*<br/>
Базовое значение другого `ComPtrRef` объекта.

### <a name="remarks"></a>Remarks

Инициализирует новый экземпляр `ComPtrRef` класса от `ComPtrRef` указанного указателя к другому объекту.

## <a name="comptrrefgetaddressof"></a><a name="getaddressof"></a>ComPtrRef:GetAddressOf

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес указателя на интерфейс, представленный `ComPtrRef` текущим объектом.

### <a name="remarks"></a>Remarks

Извлекает адрес указателя на интерфейс, представленный `ComPtrRef` текущим объектом.

## <a name="comptrrefoperator"></a><a name="operator-equality"></a>ComPtrRef::оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

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

*B*<br/>
Ссылка на `ComPtrRef` другой объект, или указатель`void*`на анонимный тип ().

### <a name="return-value"></a>Возвращаемое значение

Первый оператор дает **истинно,** если объект *a* равен объекту *b;* в противном случае, **ложные**.

Второй и третий операторы **дают истинное,** если объект *a* равен **nullptr;** в противном случае, **ложные**.

Четвертый и пятый операторы **дают истинное,** если объект *a* равен объекту *b;* в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Определение равенства двух объектов `ComPtrRef`.

## <a name="comptrrefoperator"></a><a name="operator-inequality"></a>ComPtrRef::оператор!

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

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

*B*<br/>
Ссылка на `ComPtrRef` другой объект, или указатель`void*`на анонимный объект ( ).

### <a name="return-value"></a>Возвращаемое значение

Первый оператор дает **истинно,** если объект *a* не равен объекту *b;* в противном случае, **ложные**.

Второй и третий операторы **дают истинное,** если объект *a* не равен **nullptr;** в противном случае, **ложные**.

Четвертый и пятый операторы **дают истинное,** если объект *a* не равен объекту *b;* в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Определяет неравенство двух объектов `ComPtrRef`.

## <a name="comptrrefoperator-interfacetype"></a><a name="operator-interfacetype-star-star"></a>ComPtrRef::оператор ИнтерфейсТип

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Remarks

Удаляет текущий `ComPtrRef` объект и возвращает указатель в указатель на интерфейс, представленный `ComPtrRef` объектом.

## <a name="comptrrefoperator"></a><a name="operator-star"></a>ComPtrRef:оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный `ComPtrRef` текущим объектом.

### <a name="remarks"></a>Remarks

Извлекает указатель на интерфейс, представленный `ComPtrRef` текущим объектом.

## <a name="comptrrefoperator-t"></a><a name="operator-t-star"></a>ComPtrRef::оператор ТЗ

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
operator T*();
```

### <a name="remarks"></a>Remarks

Возвращает значение [ptr_](comptrrefbase-class.md#ptr) члена данных `ComPtrRef` текущего объекта.

## <a name="comptrrefoperator-void"></a><a name="operator-void-star-star"></a>ComPtrRef::оператор пустота\*\*

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Remarks

Удаляет текущий `ComPtrRef` объект, отбрасывает указатель на интерфейс, который `ComPtrRef` был представлен объектом в качестве `void`указателя на указатель к указателю, а затем возвращает указатель.

## <a name="comptrrefreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtrRef::ReleaseandgetAddressof

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный удаленным `ComPtrRef` объектом.

### <a name="remarks"></a>Remarks

Удаляет текущий `ComPtrRef` объект и возвращает указатель в указатель на интерфейс, представленный `ComPtrRef` объектом.
