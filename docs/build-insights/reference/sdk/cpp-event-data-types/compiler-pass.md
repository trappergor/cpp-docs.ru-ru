---
title: Класс CompilerPass
description: Ссылка на класс SDK CompilerPass.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 11af981b647d5183f88dad024d90c0ef4f8a28bc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325045"
---
# <a name="compilerpass-class"></a>Класс CompilerPass

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `CompilerPass` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS](../event-table.md#front-end-pass) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class CompilerPass : public Activity
{
public:
    enum class PassCode
    {
        FRONT_END,
        BACK_END
    };

    CompilerPass(const RawEvent& event);

    PassCode       PassCode() const;
    const wchar_t* InputSourcePath() const;
    const wchar_t* OutputObjectPath() const;
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `CompilerPass` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[CompilerPass](#compiler-pass)

### <a name="enums"></a>Перечисления

#### <a name="passcode"></a>Пароль

|||
|-|-|
|FRONT_END|Передний проход.|
|BACK_END|Обратный проход.|

### <a name="functions"></a>Функции

[ВхотливыйИсточникПат](#input-source-path)\
[ВыходОбъектПат](#output-object-path)\
[Пароль](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a>CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS.](../event-table.md#front-end-pass)

## <a name="inputsourcepath"></a><a name="input-source-path"></a>ВхотливыйИсточникПат

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к исходному файлу ввода, обрабатываемый этим компилятором.

## <a name="outputobjectpath"></a><a name="output-object-path"></a>ВыходОбъектПат

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к файлу объекта вывода, производимому этим проходом компилятора.

## <a name="passcode"></a><a name="pass-code"></a>Пароль

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий, какой проход компилятора представлен этим объектом CompilerPass.

::: moniker-end
