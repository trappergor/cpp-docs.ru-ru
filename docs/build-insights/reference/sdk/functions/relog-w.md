---
title: RelogW
description: Справочник по классу RelogW пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e01cf7ca769c60761999ca320a7f9a65b41a8ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920064"
---
# <a name="relogw"></a>RelogW

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Функция `RelogW` используется для чтения событий MSVC из входной трассировки событий Windows (ETW) и записи этих событий в новую, измененную трассировку ETW.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
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
