---
title: перечисление с порядком байтов
description: Enum, используемое для указания порядок следования байтов скалярных типов
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: 78df181e20d0e5d72508bd0fc86118528a312d6b
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194768"
---
# <a name="endian-enum"></a>перечисление с порядком байтов

Указывает порядок следования байтов всех скалярных типов.

## <a name="syntax"></a>Синтаксис

```cpp
enum class endian {
    little = 0,
    big = 1,
    native = little
 };
```

### <a name="members"></a>Участники

|Элемент|Описание|
|-|-|
| `little` | Указывает, что скалярные типы имеют прямой порядок байтов. То есть наименьший значащий байт хранится в наименьшем адресе. Например, `0x1234` хранится `0x34` `0x12` .  |
| `big` | Указывает, что скалярные типы имеют обратный порядок байтов, то есть наиболее значимый байт хранится в наименьшем адресе. Например, `0x1234` хранится `0x12` `0x34` .  |

## <a name="remarks"></a>Remarks

Все собственные скалярные типы имеют прямой порядок байтов для платформ, Microsoft Visual C++ целевых объектов (x86, x64, ARM, ARM64).

## <a name="requirements"></a>Требования

**Заголовок:**\<bit>

**Пространство имен:** std

`/std:c++latest` является обязательным

## <a name="see-also"></a>См. также раздел

[\<bit>](../standard-library/bit.md)  
