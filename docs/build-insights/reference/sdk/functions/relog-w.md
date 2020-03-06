---
title: релогв
description: Справочник C++ по функциям SDK для Build Insights релогв.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 563b1aa92877ff5bc1216bc914c1c661de06dfc0
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334292"
---
# <a name="relogw"></a>релогв

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `RelogW` используется для чтения событий КОМПИЛЯТОРОМ MSVC из трассировки входных данных трассировки событий Windows (ETW) и их записи в новую, измененную трассировку ETW.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Параметры

*инпутлогфиле*\
Входная трассировка ETW, из которой требуется считать события.

*аутпутлогфиле*\
Файл, в который записываются новые события.

*релогдескриптор*\
Указатель на объект [RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) . Используйте этот объект для настройки сеанса повторного ведения журнала.

### <a name="return-value"></a>Возвращаемое значение

Код результата из перечисления [RESULT_CODE](../other-types/result-code-enum.md) .

::: moniker-end
