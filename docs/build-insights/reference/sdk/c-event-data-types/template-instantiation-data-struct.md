---
title: Структура TEMPLATE_INSTANTIATION_DATA
description: В C++ пакете SDK для аналитики сборки TEMPLATE_INSTANTIATION_DATA ссылка на структуру.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9aa669d715dbe56ce7e889330f46f307f520710f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335084"
---
# <a name="template_instantiation_data-structure"></a>Структура TEMPLATE_INSTANTIATION_DATA

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TEMPLATE_INSTANTIATION_DATA` описывает создание экземпляра шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>Члены

|  |  |
|--|--|
| `SpecializationSymbolKey` | Ключ для типа специализации шаблона. Это значение уникально в анализируемой трассировке. |
| `PrimaryTemplateSymbolKey` | Ключ для типа основного шаблона, который был специализированным. Это значение уникально в анализируемой трассировке. |
| `KindCode` | Тип экземпляра шаблона. Дополнительные сведения см. в разделе [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md). |

## <a name="remarks"></a>Remarks

Ключи в структуре `TEMPLATE_INSTANTIATION_DATA` уникальны в анализируемой трассировке. Однако два разных ключа, поступающих от разных проходов внешнего интерфейса компилятора, могут указывать на два идентичных типа. При использовании `TEMPLATE_INSTANTIATION_DATA` данных из нескольких интерфейсных проходов компилятора используйте события [SYMBOL_NAME](../event-table.md#symbol-name) , чтобы определить, совпадают ли два типа. `SymbolName` события выдаются в конце внешнего прохода компилятора, после того, как все экземпляры шаблонов созданы.

::: moniker-end
