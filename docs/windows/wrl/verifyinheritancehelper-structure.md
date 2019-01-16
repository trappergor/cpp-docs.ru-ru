---
title: VerifyInheritanceHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: c37a0eb74fd65b3d349d5b8b7c792fbaf7d1ac9a
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337703"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
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

Имя                                       | Описание:
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper::Verify](#verify) | Проверяет два интерфейса, указанные параметрами шаблона и определяет, является ли один интерфейс производным от другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInheritanceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="verify"></a>VerifyInheritanceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет два интерфейса, указанные параметрами шаблона и определяет, является ли один интерфейс производным от другого.

Если это условие не выполняется, выдается ошибка.
