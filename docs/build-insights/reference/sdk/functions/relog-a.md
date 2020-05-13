---
title: Релога
description: Ссылка на функцию «Исследования сборки SDK RelogA».
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5a772b1156fc69eeef39514afe401c549c3b7c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323846"
---
# <a name="reloga"></a>Релога

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `RelogA` используется для чтения событий MSVC из трассировки событий для отслеживания Windows (ETW) и записывания их в новый, измененный след ETW.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>Параметры

*вхотливыйLogFile*\
Входный след ETW, из которого вы хотите прочитать события.

*выходНопок*\
Файл, в котором можно написать новые события.

*релогДескриптор*\
Указатель на [RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) объект. Используйте этот объект для настройки сеанса перезаписи.

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

::: moniker-end
