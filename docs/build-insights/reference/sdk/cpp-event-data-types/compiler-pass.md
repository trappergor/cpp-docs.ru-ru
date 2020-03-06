---
title: Класс Компилерпасс
description: Справочник C++ по классу SDK для Build Insights компилерпасс.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CompilerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c2fa1c2c4be8aaf5bec77b383f93a4b033ca8e3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334958"
---
# <a name="compilerpass-class"></a>Класс Компилерпасс

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `CompilerPass` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS](../event-table.md#front-end-pass) события.

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

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `CompilerPass` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[компилерпасс](#compiler-pass)

### <a name="enums"></a>Перечисления

#### <a name="passcode"></a>Пароль

|||
|-|-|
|FRONT_END|Клиентский этап передачи.|
|BACK_END|Серверный проход.|

### <a name="functions"></a>Функции

[Инпутсаурцепас](#input-source-path)\
[Аутпутобжектпас](#output-object-path)\
[Секретный код](#pass-code)\

## <a name="compiler-pass"></a>компилерпасс

```cpp
CompilerPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BACK_END_PASS](../event-table.md#back-end-pass) или [FRONT_END_PASS](../event-table.md#front-end-pass) .

## <a name="input-source-path"></a>инпутсаурцепас

```cpp
const wchar_t* InputSourcePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к входному исходному файлу, обрабатываемому этим проходом компилятора.

## <a name="output-object-path"></a>аутпутобжектпас

```cpp
const wchar_t* OutputObjectPath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Абсолютный путь к выходному файлу объекта, созданному этим проходом компилятора.

## <a name="pass-code"></a>Пароль

```cpp
PassCode PassCode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Код, указывающий, какой проход компилятора представлен этим объектом Компилерпасс.

::: moniker-end
