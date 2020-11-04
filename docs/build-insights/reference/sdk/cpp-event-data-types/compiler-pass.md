---
title: Класс CompilerPass
description: Справочник по классу CompilerPass из пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bfbfdc28870a13a9cdb19d0ec050ea2e69fe1208
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920818"
---
# <a name="compilerpass-class"></a>Класс CompilerPass

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `CompilerPass` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте его для сопоставления события [BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS](../event-table.md#front-end-pass).

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

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `CompilerPass` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[CompilerPass](#compiler-pass)

### <a name="enums"></a>Перечисления

#### <a name="passcode"></a>PassCode

|Значение|Описание|
|-|-|
|FRONT_END|Проход внешнего интерфейса.|
|BACK_END|Проход внутреннего интерфейса.|

### <a name="functions"></a>Функции

[InputSourcePath](#input-source-path)\
[OutputObjectPath](#output-object-path)\
[PassCode](#pass-code)\

## <a name="compilerpass"></a><a name="compiler-pass"></a> CompilerPass

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS](../event-table.md#front-end-pass).

## <a name="inputsourcepath"></a><a name="input-source-path"></a> InputSourcePath

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к входному исходному файлу, обрабатываемому этим проходом компилятора.

## <a name="outputobjectpath"></a><a name="output-object-path"></a> OutputObjectPath

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к выходному объектному файлу, обрабатываемому этим проходом компилятора.

## <a name="passcode"></a><a name="pass-code"></a> PassCode

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий, какой проход компилятора представлен этим объектом CompilerPass.

::: moniker-end
