---
title: Класс Platform::STAThreadAttribute
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
ms.openlocfilehash: 9073dc6e802aa2ed6bfa4fde2a09dd8a0864687b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555670"
---
# <a name="platformstathreadattribute-class"></a>Класс Platform::STAThreadAttribute

Указывает, что потоковая модель для приложения является однопотоковым подразделением (STA).

## <a name="syntax"></a>Синтаксис

```
public ref class STAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор STAThreadAttribute 1](#ctor)|Инициализирует новый экземпляр класса.|

### <a name="public-methods"></a>Открытые методы

Атрибут STAThreadAttribute наследует от [Platform::Object Class](../cppcx/platform-object-class.md). Атрибут STAThreadAttribute также перегружает или имеет следующие члены:

|name|Описание|
|----------|-----------------|
|[STAThreadAttribute::Equals](#equals)|Определяет, равен ли заданный объект текущему объекту.|
|[STAThreadAttribute::GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|
|[STAThreadAttribute::ToString](#tostring)|Возвращает строку, представляющую текущий объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Platform`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform

## <a name="ctor"></a> STAThreadAttribute constructor

Инициализирует новый экземпляр класса STAThreadAttribute.

### <a name="syntax"></a>Синтаксис

```cpp
public:STAThreadAttribute();
```

## <a name="equals"></a> STAThreadAttribute::Equals

Определяет, равен ли заданный объект текущему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объекты равны; в противном случае — значение **false**.

## <a name="gethashcode"></a> STAThreadAttribute::GetHashCode

Возвращает хэш-код данного экземпляра.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Хэш-код данного экземпляра.

## <a name="tostring"></a> STAThreadAttribute::ToString

Возвращает строку, представляющую текущий объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, представляющая текущий объект.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)