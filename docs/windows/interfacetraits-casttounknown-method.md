---
title: Метод InterfaceTraits::CastToUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: aca47fa0-3c60-47f2-a73c-258f7160adff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df27ec7ca4cccb278fee524aab9d0d2dc5a25134
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589763"
---
# <a name="interfacetraitscasttounknown-method"></a>Метод InterfaceTraits::CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*  
Тип параметра *ptr*.

*ptr*  
Указатель на тип *T*.

## <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUnknown, из которого `Base` является производным.

## <a name="remarks"></a>Примечания

Приводит определенный указатель к указателю на `IUnknown`.

Дополнительные сведения о `Base`, см. в разделе общедоступные определения типов в [interfacetraits-структура](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура InterfaceTraits](../windows/interfacetraits-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)