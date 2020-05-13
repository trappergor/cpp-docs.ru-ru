---
title: Класс значения Platform::SizeT
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 5add9212dc2655bc37cd357741073f855b009bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322151"
---
# <a name="platformsizet-value-class"></a>Класс значения Platform::SizeT

Представляет размер объекта. SizeT — беззнаковый тип данных.

## <a name="syntax"></a>Синтаксис

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Участники

|Участник|Описание|
|------------|-----------------|
|[Конструктор SizeT::SizeT](#ctor)|Инициализирует новый экземпляр класса, используя указанное значение.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="sizetsizet-constructor"></a><a name="ctor"></a>Размер:SizeT конструктор

Инициализирует новый экземпляр класса SizeT указанным значением.

### <a name="syntax"></a>Синтаксис

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Параметры

*значение1*<br/>
32-битовое значение без знака.

*значение2*<br/>
Указатель на 32-разрядное значение без знака.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
