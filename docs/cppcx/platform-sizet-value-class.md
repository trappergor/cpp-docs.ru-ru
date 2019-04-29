---
title: Класс значения Platform::SizeT
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 7f81cb9e1fc2ef7a74cb3878c369e4d7d14e3d90
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330145"
---
# <a name="platformsizet-value-class"></a>Класс значения Platform::SizeT

Представляет размер объекта. SizeT — беззнаковый тип данных.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Участники

|Член|Описание|
|------------|-----------------|
|[Конструктор SizeT::SizeT](#ctor)|Инициализирует новый экземпляр класса, используя указанное значение.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="ctor"></a>  Конструктор SizeT::SizeT

Инициализирует новый экземпляр класса SizeT указанным значением.

### <a name="syntax"></a>Синтаксис

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Параметры

*Значение1*<br/>
32-битовое значение без знака.

*Value2*<br/>
Указатель на 32-разрядное значение без знака.

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
