---
title: Метод InterfaceTraits::Verify | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 46edd67f-7952-4552-a157-55e823f616c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c6491968541a0015110c55edf2bede40c084947
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583448"
---
# <a name="interfacetraitsverify-method"></a>Метод InterfaceTraits::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline static void Verify();
```

## <a name="remarks"></a>Примечания

Проверяет, что `Base` должным образом является производным.

Дополнительные сведения о `Base`, см. в разделе **общедоступные определения типов** статьи [interfacetraits-структура](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура InterfaceTraits](../windows/interfacetraits-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)