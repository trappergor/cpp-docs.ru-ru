---
title: Метод ComPtr::Detach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 84db0a82dfe6f9333f6a533aa9bc2bb529854fa2
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593416"
---
# <a name="comptrdetach-method"></a>Метод ComPtr::Detach

Отменяет связь этого **ComPtr** объекта с интерфейсом, который он представляет.

## <a name="syntax"></a>Синтаксис

```cpp
T* Detach();
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс, который был представлен этим **ComPtr** объекта.

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс ComPtr](../windows/comptr-class.md)