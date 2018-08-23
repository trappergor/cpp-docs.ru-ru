---
title: Метод Implements::CastToUnknown | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 988580a34c030c84c50adfff2741408be4b249cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586362"
---
# <a name="implementscasttounknown-method"></a>Метод Implements::CastToUnknown

Возвращает указатель на базовый `IUnknown` интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline IUnknown* CastToUnknown();
```

## <a name="return-value"></a>Возвращаемое значение

Эта операция выполняется успешно и всегда возвращает `IUnknown` указатель.

## <a name="remarks"></a>Примечания

Внутренняя вспомогательная функция.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Структура Implements](../windows/implements-structure.md)