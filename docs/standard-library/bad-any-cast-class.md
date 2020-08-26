---
title: Класс bad_any_cast
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: b47ca4f615c6f317f17ce64e8388ae5d698185ea
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844591"
---
# <a name="bad_any_cast-class"></a>Класс bad_any_cast

Объекты, созданные при сбое `any_cast` .

## <a name="syntax"></a>Синтаксис

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>Функции элементов

|Имя|Описание|
|-|-|
|[What](#what)|Возвращает тип.|

## <a name="what"></a><a name="what"></a> What

Возвращает тип.

```cpp
const char* what() const noexcept override;
```
