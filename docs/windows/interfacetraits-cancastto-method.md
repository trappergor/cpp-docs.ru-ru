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
ms.openlocfilehash: 705b495e3f6d626a742fd1a63989c8cc658446a4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379672"
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

*ptr*<br/>
Имя указателя на тип.

*riid*<br/>
Идентификатор интерфейса `Base`.

*ppv*<br/>
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

[Структура InterfaceTraits](../windows/interfacetraits-structure.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)