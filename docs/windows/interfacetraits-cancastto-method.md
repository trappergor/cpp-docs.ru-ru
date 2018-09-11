---
title: Метод InterfaceTraits::CanCastTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aea326149c9748ff480d523a1078f54ba733cb14
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610424"
---
# <a name="interfacetraitscancastto-method"></a>Метод InterfaceTraits::CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*ptr*  
Имя указателя на тип.

*riid*  
Идентификатор интерфейса `Base`.

*ppv*  
Если операция выполнена успешно, *ppv* указывает на интерфейсе, указанном свойством `Base`. В противном случае *ppv* присваивается **nullptr**.

## <a name="return-value"></a>Возвращаемое значение

**значение true,** при успешном выполнении этой операции и *ptr* приведен к указателю на `Base`; в противном случае **false** .

## <a name="remarks"></a>Примечания

Указывает ли заданный указатель может быть приведен к указателю на `Base`.

Дополнительные сведения о `Base`, см. в разделе **общедоступные определения типов** статьи [interfacetraits-структура](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура InterfaceTraits](../windows/interfacetraits-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)