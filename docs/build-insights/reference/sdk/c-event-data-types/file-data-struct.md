---
title: Структура FILE_DATA
description: Справочник по структуре FILE_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b5f793df0340005665a8f4ab42e9793f51f3aa0c
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041813"
---
# <a name="file_data-structure"></a>Структура FILE_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В структуре `FILE_DATA` описываются входные или выходные данные файла.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct FILE_DATA_TAG
{
    const wchar_t*      Path;
    int                 TypeCode;

} FILE_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `Path` | Абсолютный путь к файлу |
| `TypeCode` | Код, описывающий тип файла. Дополнительные сведения см. в статье о [FILE_TYPE_CODE](file-type-code-enum.md). |

::: moniker-end
