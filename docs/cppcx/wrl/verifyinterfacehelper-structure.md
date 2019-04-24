---
title: VerifyInterfaceHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: cdd0272953b2399cd71efe207eb1c56e5de154e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785001"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper - структура

Поддерживает инфраструктуру библиотека шаблонов C++ среды выполнения Windows и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Параметры

*I*<br/>
Интерфейс для проверки.

*isWinRTInterface*

## <a name="remarks"></a>Примечания

Проверяет, что интерфейс, указанный в параметре шаблона соответствует определенным требованиям.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

name                                            | Описание
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[Метод VerifyInterfaceHelper::Verify](#verify) | Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInterfaceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="verify"></a>VerifyInterfaceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.
