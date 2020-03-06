---
title: Структура FILE_DATA
description: В C++ пакете SDK для аналитики сборки FILE_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72cae8c8eb81bdb8d94897c46c5af90c89e92ab4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335198"
---
# <a name="file_data-structure"></a>Структура FILE_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `FILE_DATA` описывает входные или выходные данные файла.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `Path` | Абсолютный путь к файлу |
| `TypeCode` | Код, описывающий тип файла. Дополнительные сведения см. в разделе [FILE_TYPE_CODE](file-type-code-enum.md). |

::: moniker-end
