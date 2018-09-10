---
title: Класс is_nothrow_destructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 245dd02a8077d652baae87d678122830f95869bc
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110348"
---
# <a name="isnothrowdestructible-class"></a>Класс is_nothrow_destructible

Проверяет, является ли тип уничтожаемым и знает ли компилятор, что деструктор не выдает исключения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* — Уничтожаемый, а деструктор известен компилятору не будет выдавать. В противном случае — значение false.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
