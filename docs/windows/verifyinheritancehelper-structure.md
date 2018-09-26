---
title: Verifyinheritancehelper-структура | Документация Майкрософт
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6231345b837cae8f36e8441173300d804c0ea167
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169637"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename I,
   typename Base
>
struct VerifyInheritanceHelper;
template <
   typename I
>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Параметры

*I*<br/>
Тип.

*Base*<br/>
Другой тип.

## <a name="remarks"></a>Примечания

Проверяет, является ли один интерфейс является производным от другого интерфейса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                                       | Описание
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper::Verify](#verify) | Проверяет два интерфейса, указанные параметрами шаблона и определяет, является ли один интерфейс производным от другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInheritanceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="verify"></a>VerifyInheritanceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет два интерфейса, указанные параметрами шаблона и определяет, является ли один интерфейс производным от другого.

Если это условие не выполняется, выдается ошибка.
