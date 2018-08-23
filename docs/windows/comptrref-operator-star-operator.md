---
title: Оператор ComPtrRef::operator * | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5bb6bc06f65f53f919197b5350db8aacc268013f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602963"
---
# <a name="comptrrefoperator-operator"></a>Оператор ComPtrRef::operator*

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
InterfaceType* operator *();
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, представленный текущим **ComPtrRef** объекта.

## <a name="remarks"></a>Примечания

Извлекает указатель на интерфейс, представленный текущим **ComPtrRef** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс ComPtrRef](../windows/comptrref-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)