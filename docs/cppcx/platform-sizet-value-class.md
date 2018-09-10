---
title: Класс значения Platform::sizet | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs:
- C++
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b78d205956f026fe730848afa4c0d6fe7b52b52c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102006"
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