---
title: Перечисление FILE_TYPE_CODE
description: Справочник по перечислению FILE_TYPE_CODE пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FILE_TYPE_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ddd625829e94786c0daddf0e78b914e225b2ecfb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921027"
---
# <a name="file_type_code-enum"></a>Перечисление FILE_TYPE_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `FILE_TYPE_CODE` используется для описания типа файла.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `FILE_TYPE_CODE_OTHER` | 0 (0x00000000) | Тип файла, не указанный в этом перечислении. |
| `FILE_TYPE_CODE_OBJ` | 1 (0x00000001) | Файл объекта (\*.obj). |
| `FILE_TYPE_CODE_EXECUTABLE_IMAGE` | 2 (0x00000002) | Исполняемый файл (\*.exe) или DLL-файл (\*.dll). |
| `FILE_TYPE_CODE_LIB` | 3 (0x00000003) | Файл статической библиотеки (*.lib). |
| `FILE_TYPE_CODE_IMP_LIB` | 4 (0x00000004) | Библиотека импорта (*.lib). |
| `FILE_TYPE_CODE_EXP` | 5 (0x00000005) | Файл экспорта (*.exp). |

## <a name="remarks"></a>Комментарии

::: moniker-end
