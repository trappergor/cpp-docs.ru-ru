---
title: Перечисление FILE_TYPE_CODE
description: В C++ пакете SDK для аналитики сборки FILE_TYPE_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e64f9315c62ce40c436032d6c96fdfa725847a7f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335168"
---
# <a name="file_type_code-enum"></a>Перечисление FILE_TYPE_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `FILE_TYPE_CODE` описывает тип файла.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | Тип файла, не указанный в этом перечислении. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Объект (\*OBJ-файл). |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Исполняемый файл (\*. exe) или DLL (\*. dll). |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Файл статической библиотеки (*. lib). |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | Библиотека импорта (*. lib) |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Файл экспорта (*. exp). |

## <a name="remarks"></a>Remarks

::: moniker-end
