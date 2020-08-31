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
ms.openlocfilehash: 054bdf75dcfca42b8c202565fb44df671f17f912
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831623"
---
# <a name="compilerpass-class"></a>Класс CompilerPass

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

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
