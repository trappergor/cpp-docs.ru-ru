---
title: Класс is_trivially_copyable | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19bed4a455ea2b0b894ba842f349aa304e9f261d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964687"
---
# <a name="istriviallycopyable-class"></a>Класс is_trivially_copyable

Проверяет, является ли тип тривиально копируемым.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Параметры

*T* запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является тривиально копируемым, в противном случае он содержит значение false. Тривиально копируемые типы не имеют нетривиальных операций копирования, операций перемещения и деструкторов. Как правило, операция копирования считается тривиальной, если она может быть реализована как побитовое копирование. Встроенные типы и массивы тривиально копируемых типов являются тривиально копируемыми.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
