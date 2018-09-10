---
title: Класс Platform::MTAThreadAttribute | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::MTAThreadAttribute::Equals
- VCCORLIB/Platform::MTAThreadAttribute::GetHashCode
- VCCORLIB/Platform::MTAThreadAttribute::ToString
dev_langs:
- C++
helpviewer_keywords:
- Platform::MTAThreadAttribute Class
ms.assetid: bfc546a7-4333-4407-85b4-4721565e1f44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc6405337814671d6789c8364e2f458c84d2487a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109710"
---
# <a name="platformmtathreadattribute-class"></a>Класс Platform::MTAThreadAttribute

Указывает, что потоковая модель для приложения является многопотоковым подразделением (MTA).

## <a name="syntax"></a>Синтаксис

```
public ref class MTAThreadAttribute sealed : Attribute
```

### <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[1 конструктор MTAThreadAttribute](#ctor) конструктор|Инициализирует новый экземпляр класса.|

### <a name="public-methods"></a>Открытые методы

Атрибут MTAThreadAttribute наследует от [Platform::Object Class](../cppcx/platform-object-class.md). Атрибут MTAThreadAttribute также перегружает или имеет следующие члены:

|name|Описание|
|----------|-----------------|
|[MTAThreadAttribute::Equals](#equals)|Определяет, равен ли заданный объект текущему объекту.|
|[MTAThreadAttribute::GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|
|[MTAThreadAttribute::ToString](#tostring)|Возвращает строку, представляющую текущий объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Platform`

### <a name="requirements"></a>Требования

**Метаданные:** platform.winmd

**Пространство имен:** Platform

## <a name="ctor"></a> Конструктор MTAThreadAttribute

Инициализирует новый экземпляр класса MTAThreadAttribute.

### <a name="syntax"></a>Синтаксис

```cpp
public:MTAThreadAttribute();
```

## <a name="equals"></a> MTAThreadAttribute::Equals

Определяет, равен ли заданный объект текущему объекту.

### <a name="syntax"></a>Синтаксис

```cpp
public:virtual override bool Equals( Object^ obj );
```

### <a name="parameters"></a>Параметры

*obj*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если объекты равны, в противном случае — значение `false`.

## <a name="gethashcode"></a> MTAThreadAttribute::GetHashCode

Возвращает хэш-код данного экземпляра.

### <a name="syntax"></a>Синтаксис

```cpp
public:int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Хэш-код данного экземпляра.

## <a name="tostring"></a> MTAThreadAttribute::ToString

Возвращает строку, представляющую текущий объект.

### <a name="syntax"></a>Синтаксис

```cpp
public:String^ ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Строка, представляющая текущий объект.

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)