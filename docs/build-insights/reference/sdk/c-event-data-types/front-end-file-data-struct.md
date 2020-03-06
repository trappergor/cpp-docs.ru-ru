---
title: Структура FRONT_END_FILE_DATA
description: В C++ пакете SDK для аналитики сборки FRONT_END_FILE_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 33232a0f83566e58e64964e84961a7ade2de7b7c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335186"
---
# <a name="front_end_file_data-structure"></a>Структура FRONT_END_FILE_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `FRONT_END_FILE_DATA` описывает обработку файла внешним интерфейсом компилятора.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `Path` | Абсолютный путь к файлу в кодировке UTF-8. |

::: moniker-end
