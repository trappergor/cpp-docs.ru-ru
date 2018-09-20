---
title: Метод ChainInterfaces::FillArrayWithIid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17e1f47c2dfaf53b63e6bc672cb7822f9bf2b391
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375350"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>Метод ChainInterfaces::FillArrayWithIid

Идентификатор интерфейса определяется хранилищ *I0* параметр шаблона в указанном расположении в указанном массиве идентификаторов интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*<br/>
Указатель на значение индекса в *идентификаторы IID* массива.

*идентификаторы IID*<br/>
Массив идентификаторов интерфейсов.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Структура ChainInterfaces](../windows/chaininterfaces-structure.md)