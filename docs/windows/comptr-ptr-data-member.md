---
title: Элемент данных Comptr::ptr_ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ptr_
dev_langs:
- C++
helpviewer_keywords:
- ptr_ data member
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c1e1a8bc076144d80358191cd8eca209057b869
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599181"
---
# <a name="comptrptr-data-member"></a>Элемент данных ComPtr::ptr_

Содержит указатель на интерфейс, который связан с и управляемые этим экземпляром **ComPtr**.

## <a name="syntax"></a>Синтаксис

```cpp
InterfaceType *ptr_;
```

## <a name="remarks"></a>Примечания

**ptr_** является членом внутреннего, защищенных данных.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)