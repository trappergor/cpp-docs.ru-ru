---
title: Класс is_trivially_destructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f83d6ace116d48e9c117724b5b408721de625c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallydestructible-class"></a>Класс is_trivially_destructible

Проверяет, можно ли уничтожить тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_destructible;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `T` — уничтожаемый, а деструктор известен компилятору как не использующий нетривиальные операции. В противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
