---
title: Factorycache-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d56779b5df33f75c9147d34b55f8c2fc65204a82
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234545"
---
# <a name="factorycache-structure"></a>FactoryCache - структура

Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Примечания

Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный среды выполнения Windows или COM-класса объекта.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                              | Описание
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache::cookie](#cookie)   | Содержит значение, которое идентифицирует зарегистрированный объект среды выполнения Windows или COM-класса, а впоследствии будет использоваться для отмены регистрации объекта.
[FactoryCache::factory](#factory) | Указывает на фабрику классов среды выполнения Windows или COM.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FactoryCache`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="cookie"></a>FactoryCache::cookie

Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Примечания

Содержит значение, которое идентифицирует зарегистрированный объект среды выполнения Windows или COM-класса, а впоследствии будет использоваться для отмены регистрации объекта.

## <a name="factory"></a>FactoryCache::factory

Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Примечания

Указывает на фабрику классов среды выполнения Windows или COM.
