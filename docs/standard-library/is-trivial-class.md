---
title: Класс is_trivial | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivial
dev_langs:
- C++
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b30b634a84dc47d839e1288bc34437b440e914c3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864126"
---
# <a name="istrivial-class"></a>Класс is_trivial

Проверяет, является ли тип тривиальным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` является тривиальным, в противном случае — значение false. К тривиальным типам относятся скалярные типы, типы тривиально копируемых классов, массивы этих типов и версии типов с квалификатором cv.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
