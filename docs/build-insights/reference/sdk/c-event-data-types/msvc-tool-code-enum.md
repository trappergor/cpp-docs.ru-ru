---
title: Перечисление MSVC_TOOL_CODE
description: Справочник по перечислению MSVC_TOOL_CODE пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MSVC_TOOL_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4f539401f304d5d39983ec8f97cc8c99b19399d9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920961"
---
# <a name="msvc_tool_code-enum"></a>Перечисление MSVC_TOOL_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `MSVC_TOOL_CODE`.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `MSVC_TOOL_CODE_CL` | 0 (0x00000000) | Компилятор (cl.exe). |
| `MSVC_TOOL_CODE_LINK` | 1 (0x00000001) | Компоновщик (link.exe). |

## <a name="remarks"></a>Комментарии

Используется в функциях пакета SDK для C.

::: moniker-end
