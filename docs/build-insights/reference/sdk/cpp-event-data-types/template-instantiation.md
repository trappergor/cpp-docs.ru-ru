---
title: Класс TemplateInstantiation
description: Справочник по классу TemplateInstantiation пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7ff03aaa431f5c5e217f605698a255686411b479
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920441"
---
# <a name="templateinstantiation-class"></a>Класс TemplateInstantiation

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `TemplateInstantiation` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation).

## <a name="syntax"></a>Синтаксис

```cpp
class TemplateInstantiation : public Activity
{
public:
    enum class Kind
    {
        CLASS       = TEMPLATE_INSTANTIATION_KIND_CODE_CLASS,
        FUNCTION    = TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION,
        VARIABLE    = TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE,
        CONCEPT     = TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT
    };

    TemplateInstantiation(const RawEvent& event);

    const unsigned long long& SpecializationSymbolKey() const;
    const unsigned long long& PrimaryTemplateSymbolKey() const;

    Kind Kind() const;
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `TemplateInstantiation` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[TemplateInstantiation](#template-instantiation)

### <a name="functions"></a>Функции

[Kind](#kind)
[PrimaryTemplateSymbolKey](#primary-template-symbol-key)
[SpecializationSymbolKey](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a> Kind

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип выполненной операции создания экземпляра шаблона.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a> PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа шаблона, который был специализирован. Этот идентификатор уникален в пределах этапа внешнего интерфейса компилятора.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a> SpecializationSymbolKey

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа специализации. Этот идентификатор уникален в пределах этапа внешнего интерфейса компилятора.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a> TemplateInstantiation

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation).

::: moniker-end
