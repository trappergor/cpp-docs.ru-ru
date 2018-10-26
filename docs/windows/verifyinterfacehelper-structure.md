---
title: Verifyinterfacehelper-структура | Документация Майкрософт
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b70155566695ade6b6778ade3b4758faebb3ea67
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788869"
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

Имя                                            | Описание
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[Метод VerifyInterfaceHelper::Verify](#verify) | Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInterfaceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="verify"></a>VerifyInterfaceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.
