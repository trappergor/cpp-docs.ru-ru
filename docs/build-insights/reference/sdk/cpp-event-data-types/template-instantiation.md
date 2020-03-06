---
title: Класс Темплатеинстантиатион
description: Справочник C++ по классу SDK для Build Insights темплатеинстантиатион.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2c94f8d3a4613e072c03f6dd4c846798d3d2122b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334526"
---
# <a name="templateinstantiation-class"></a>Класс Темплатеинстантиатион

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TemplateInstantiation` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [TEMPLATE_INSTANTIATIONного](../event-table.md#template-instantiation) события.

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

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `TemplateInstantiation` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[темплатеинстантиатион](#template-instantiation)

### <a name="functions"></a>Функции

[Kind](#kind)
[примаритемплатесимболкэй](#primary-template-symbol-key)
[спеЦиализатионсимболкэй](#specialization-symbol-key)

## <a name="kind"></a>Особого

```cpp
Kind Kind() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, описывающий тип выполненного создания экземпляра шаблона.

## <a name="primary-template-symbol-key"></a>примаритемплатесимболкэй

```cpp
const unsigned long long& PrimaryTemplateSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа шаблона, который был специализированным. Этот идентификатор уникален в рамках внешнего прохода компилятора.

## <a name="specialization-symbol-key"></a>спеЦиализатионсимболкэй

```cpp
const unsigned long long& SpecializationSymbolKey() const;
```

### <a name="return-value"></a>Возвращаемое значение

Числовой идентификатор для типа специализации. Этот идентификатор уникален в рамках внешнего прохода компилятора.

## <a name="template-instantiation"></a>темплатеинстантиатион

```cpp
TemplateInstantiation(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

::: moniker-end
