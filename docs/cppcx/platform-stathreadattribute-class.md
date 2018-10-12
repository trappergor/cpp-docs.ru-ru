---
title: Класс Platform::STAThreadAttribute | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb97be3012ae4a7c21765d33904f0914d7530025
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162052"
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