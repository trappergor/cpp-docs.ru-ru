---
title: RelogA
description: Справочник по классу RelogA пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e4882bca2241c520d4cb6ba0a8eb9c32704eaef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922803"
---
# <a name="reloga"></a>RelogA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `RelogA` используется для чтения событий MSVC из трассировки событий Windows (ETW) и записи этих событий в новую, измененную трассировку ETW.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Параметры

*inputLogFile*\
Входная трассировка ETW, из которой нужно считать события.

*outputLogFile*\
Файл, в который записываются новые события.

*relogDescriptor*\
Указатель на объект [RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md). Используйте этот объект для настройки сеанса повторной записи в журнал.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md).

::: moniker-end
