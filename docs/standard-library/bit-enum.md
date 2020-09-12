---
title: Перечисление с порядком байтов
description: Enum, используемое для указания порядок следования байтов скалярных типов
ms.date: 08/27/2020
f1_keywords:
- bit/std::endian
helpviewer_keywords:
- std::endian
ms.openlocfilehash: b535bc009fbdc0b047444a6bc2ca36eed7a6d1cb
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040084"
---
# <a name="endian-enum"></a>Перечисление с порядком байтов

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

## <a name="remarks"></a>Комментарии

Все собственные скалярные типы имеют прямой порядок байтов для платформ, Microsoft Visual C++ целевых объектов (x86, x64, ARM, ARM64).

## <a name="requirements"></a>Требования

**Заголовок:**\<bit>

**Пространство имен:** std

[/std: требуется более поздняя версия c + +](../build/reference/std-specify-language-standard-version.md) .

## <a name="see-also"></a>См. также раздел

[\<bit>](../standard-library/bit.md)  
