---
title: RelogW
description: Ссылка на функцию «Исследования сборки SDK RelogW».
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c5d5f6e35c7cd24d2324ce1d8a0434d9048b1d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323808"
---
# <a name="relogw"></a>RelogW

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `RelogW` используется для чтения событий MSVC из отслеживания входных событий для отслеживания Windows (ETW) и записывания их в новый, измененный след ETW.

## <a name="syntax"></a>Синтаксис

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
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
