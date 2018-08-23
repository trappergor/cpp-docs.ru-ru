---
title: Оператор ComPtrRef::operator void ** | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs:
- C++
helpviewer_keywords:
- operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 468b38dac2082e47e94e4bd52af50d77327f5ef4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590693"
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void\* \* оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
operator void**() const;
```

## <a name="remarks"></a>Примечания

Удаляет текущий **ComPtrRef** объекта, приведение указателя на интерфейс, который был представлен **ComPtrRef** объекта как указатель к указатель to **void**, а затем Возвращает указатель приведения.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Класс ComPtrRef](../windows/comptrref-class.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)