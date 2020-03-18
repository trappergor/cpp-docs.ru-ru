---
title: BoolStruct - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: cdec425e317585abbd9730447e2c4fbb19b8250a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423660"
---
# <a name="boolstruct-structure"></a>BoolStruct - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Remarks

Структура `BoolStruct` определяет, управляет ли `ComPtr` время существования объекта интерфейса. `BoolStruct` внутренне используется оператором [BoolType ()](comptr-class.md#operator-microsoft-wrl-details-booltype) .

## <a name="members"></a>Члены

### <a name="public-data-members"></a>Открытые элементы данных

Имя                          | Description
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct:: Member](#member) | Указывает, что [ComPtr](comptr-class.md) имеет значение, или не управляет временем существования объекта в интерфейсе.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BoolStruct`

## <a name="requirements"></a>Требования

**Заголовок:** internal. h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="member"></a>BoolStruct:: Member

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
int Member;
```

### <a name="remarks"></a>Remarks

Указывает, что [ComPtr](comptr-class.md) имеет значение, или не управляет временем существования объекта в интерфейсе.
