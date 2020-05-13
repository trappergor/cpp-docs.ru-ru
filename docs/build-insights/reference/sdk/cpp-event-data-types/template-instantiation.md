---
title: Класс TemplateInstantiation
description: Ссылка на класс SDK TemplateInstantiation в отношении сборки информации о создании схемы.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ba8fd10efc6a536c9160f10b19e19e17bfaaad98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324221"
---
# <a name="templateinstantiation-class"></a>Класс TemplateInstantiation

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TemplateInstantiation` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для TEMPLATE_INSTANTIATION [события.](../event-table.md#template-instantiation)

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

Наряду с унаследованные члены `TemplateInstantiation` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ШаблонМеймикция](#template-instantiation)

### <a name="functions"></a>Функции

[Вид](#kind)
[PrimaryTemplateСимволКей](#primary-template-symbol-key)
[СпециализацияСимволКей](#specialization-symbol-key)

## <a name="kind"></a><a name="kind"></a>Вид

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип мгновенного стимации шаблона, который был сделан.

## <a name="primarytemplatesymbolkey"></a><a name="primary-template-symbol-key"></a>PrimaryTemplateSymbolKey

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Численный идентификатор для специализированного типа шаблона. Этот идентификатор уникален в компиляторе переднего прохода.

## <a name="specializationsymbolkey"></a><a name="specialization-symbol-key"></a>СпециализацияСимволКей

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Численный идентификатор для типа специализации. Этот идентификатор уникален в компиляторе переднего прохода.

## <a name="templateinstantiation"></a><a name="template-instantiation"></a>ШаблонМеймикция

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [TEMPLATE_INSTANTIATION.](../event-table.md#template-instantiation)

::: moniker-end
