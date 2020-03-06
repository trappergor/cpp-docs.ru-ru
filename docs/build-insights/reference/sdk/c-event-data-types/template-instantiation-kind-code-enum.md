---
title: Перечисление TEMPLATE_INSTANTIATION_KIND_CODE
description: В C++ пакете SDK для аналитики сборки TEMPLATE_INSTANTIATION_KIND_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_KIND_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 21547b1db997cb755e6836f27efc512e1388d274
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335072"
---
# <a name="template_instantiation_kind_code-enum"></a>Перечисление TEMPLATE_INSTANTIATION_KIND_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `TEMPLATE_INSTANTIATION_KIND_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `TEMPLATE_INSTANTIATION_KIND_CODE_CLASS` | 0 (0x00000000) | Создание экземпляра шаблона класса. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION` | 1 (0x00000001) | Создание экземпляра шаблона функции. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE` | 2 (0x00000002) | Создание экземпляра переменной constexpr. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT` | 3 (0x00000003) | Создание экземпляра шаблона концепции. |

## <a name="remarks"></a>Remarks

::: moniker-end
