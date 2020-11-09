---
title: Перечисление TEMPLATE_INSTANTIATION_KIND_CODE
description: Справочник по структуре TEMPLATE_INSTANTIATION_DATA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_KIND_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ee85af4e3d7f19b1b5dc9163dab6090f5ce4e42
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920948"
---
# <a name="template_instantiation_kind_code-enum"></a>Перечисление TEMPLATE_INSTANTIATION_KIND_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `TEMPLATE_INSTANTIATION_KIND_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `TEMPLATE_INSTANTIATION_KIND_CODE_CLASS` | 0 (0x00000000) | Создание экземпляра шаблона класса. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION` | 1 (0x00000001) | Создание экземпляра шаблона функции. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE` | 2 (0x00000002) | Создание экземпляра переменной constexpr. |
| `TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT` | 3 (0x00000003) | Создание экземпляра шаблона концепции. |

## <a name="remarks"></a>Комментарии

::: moniker-end
