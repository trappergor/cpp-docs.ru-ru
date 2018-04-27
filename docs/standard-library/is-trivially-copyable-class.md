---
title: Класс is_trivially_copyable | Документы Майкрософт
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
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e2792c93b477c6d6aac4350045a506eda206eb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyable-class"></a>Класс is_trivially_copyable

Проверяет, является ли тип тривиально копируемым.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` является тривиально копируемым, в противном случае — значение false. Тривиально копируемые типы не имеют нетривиальных операций копирования, операций перемещения и деструкторов. Как правило, операция копирования считается тривиальной, если она может быть реализована как побитовое копирование. Встроенные типы и массивы тривиально копируемых типов являются тривиально копируемыми.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
