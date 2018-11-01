---
title: Класс значения Platform::IntPtr
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
ms.openlocfilehash: eda65255aa76d6a801bdc0f80c437a9dc975d8f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449144"
---
# <a name="platformintptr-value-class"></a>Класс значения Platform::IntPtr

Представляет указатель или дескриптор числа со знаком, размер которого зависит от платформы (32-разрядная или 64-разрядная).

## <a name="syntax"></a>Синтаксис

```cpp
public value struct IntPtr
```

### <a name="members"></a>Участники

Класс IntPtr имеет следующие члены:

|Член|Описание|
|------------|-----------------|
|[IntPtr::IntPtr](#ctor)|Инициализирует новый экземпляр класса IntPtr.|
|[Оператор IntPtr::op_explicit](#op-explicit)|Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.|
|[IntPtr::ToInt32](#toint32)|Преобразует текущий объект IntPtr в 32-разрядное целое число.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="ctor"> </a> IntPtr::IntPtr - конструктор

Инициализирует новый экземпляр класса IntPtr, используя указанное значение.

### <a name="syntax"></a>Синтаксис

```cpp
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );
```

### <a name="parameters"></a>Параметры

*значение*<br/>
64-разрядный дескриптор или указатель, указатель на 64-разрядное значение или 32-разрядное значение, которое можно преобразовать в 64-разрядное.

## <a name="op-explicit"> </a> Оператор IntPtr::op_explicit

Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.

### <a name="syntax"></a>Синтаксис

```cpp
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );
```

### <a name="parameters"></a>Параметры

*Значение1*<br/>
Указатель на дескриптор или IntPtr.

*Value2*<br/>
32-битовое целое число, которое можно преобразовать в IntPtr.

*значение 3*<br/>
Объект IntPtr.

### <a name="return-value"></a>Возвращаемое значение

Первый и второй операторы возвращают IntPtr. Третий оператор возвращает указатель на значение, представленное текущим объектом IntPtr.

## <a name="toint32"> </a> Метод IntPtr::ToInt32

Преобразует текущее значение IntPtr в 32-битовое целое число.

### <a name="syntax"></a>Синтаксис

```cpp
int32 IntPtr::ToInt32();
```

### <a name="return-value"></a>Возвращаемое значение

32-битовое целое число.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)