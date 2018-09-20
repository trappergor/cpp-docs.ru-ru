---
title: Метод ImplementsHelper::CastToUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc36793eba9f2500020795ef9e88e63663d350c8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402169"
---
# <a name="implementshelpercasttounknown-method"></a>Метод ImplementsHelper::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
IUnknown* CastToUnknown();
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на базовый `IUnknown` интерфейс.

## <a name="remarks"></a>Примечания

Возвращает указатель на базовый `IUnknown` интерфейса для текущего `Implements` структуры.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура ImplementsHelper](../windows/implementshelper-structure.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)