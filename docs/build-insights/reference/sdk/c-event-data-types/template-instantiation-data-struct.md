---
title: Структура TEMPLATE_INSTANTIATION_DATA
description: Справочник по структуре TEMPLATE_INSTANTIATION_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c92fbd8ee7e1fff702757d003ab3bbe0bdabd886
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923437"
---
# <a name="template_instantiation_data-structure"></a>Структура TEMPLATE_INSTANTIATION_DATA

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

В структуре `TEMPLATE_INSTANTIATION_DATA` описывается создание экземпляра шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `SpecializationSymbolKey` | Ключ для типа специализации шаблона. Это значение уникально в пределах анализируемой трассировки. |
| `PrimaryTemplateSymbolKey` | Ключ для основного типа шаблона, который был специализирован. Это значение уникально в пределах анализируемой трассировки. |
| `KindCode` | Тип специализации шаблона. Дополнительные сведения см. в статье о [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md). |

## <a name="remarks"></a>Remarks

Ключи структуры `TEMPLATE_INSTANTIATION_DATA` уникальны в пределах анализируемой трассировки. Но два разных ключа, созданных на разных этапах внешнего интерфейса компилятора, могут указывать на два одинаковых типа. При считывании информации о `TEMPLATE_INSTANTIATION_DATA`, полученной на разных этапах внешнего интерфейса компилятора, используйте события [SYMBOL_NAME](../event-table.md#symbol-name), чтобы определить, совпадают ли два типа. События `SymbolName` возникают в конце этапа внешнего интерфейса компилятора после создания всех экземпляров шаблонов.

::: moniker-end
