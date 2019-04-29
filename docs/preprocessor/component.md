---
title: component
ms.date: 04/08/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 4870860650a39d27639ad18100ba37ba14aa15c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366918"
---
# <a name="component"></a>component

Управляет сбором сведений о просмотре или зависимостях из файлов исходного кода.

## <a name="syntax"></a>Синтаксис

> **компонента #pragma (обозревателе** { **на** | **off** } [**,** **ссылки** [**,** *имя* ]] **)** \
> **компонента #pragma (minrebuild на** | **off)** \
> **компонента #pragma (возможный на** | **off)**

## <a name="remarks"></a>Примечания

### <a name="browser"></a>Браузер

Можно включить или отключить сбор информации и задать игнорирование конкретных имен по мере сбора информации.

Включение и отключение сбора информации контролирует сбор сведений о просмотре, начиная с директивы pragma. Пример:

```cpp
#pragma component(browser, off)
```

предотвращает сбор информации о просмотре компилятором.

> [!NOTE]
> Для включения сбора сведений о просмотре с помощью этой директивы #pragma [информацию об исходном коде сначала необходимо включить](../build/reference/building-browse-information-files-overview.md).

`references` Параметр может использоваться с или без *имя* аргумент. С помощью `references` без *имя* включает или выключает сбор ссылок (другие сведения о просмотре прежнему собираются, тем не менее). Пример:

```cpp
#pragma component(browser, off, references)
```

предотвращает сбор информации о ссылках компилятором.

С помощью `references` с *имя* и `off` не позволяет ссылкам на *имя* появлялись в окне сведений о просмотре. Используйте этот синтаксис, чтобы игнорировать ненужные имена и типы, уменьшая тем самым размер файлов со сведениями о просмотре. Пример:

```cpp
#pragma component(browser, off, references, DWORD)
```

игнорирует ссылки на параметр DWORD с этого момента. Вы можете включить сбор ссылок на DWORD снова с помощью `on`:

```cpp
#pragma component(browser, on, references, DWORD)
```

Это единственный способ возобновить сбор ссылок на *имя*; вы должны явно включить все *имя* , вы отключали функцию.

Чтобы предотвратить расширение препроцессор *имя* (например, расширение NULL 0), поместите его в кавычки:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>Минимальная повторная сборка

Устаревший [/Gm (включение минимального перепостроения)](../build/reference/gm-enable-minimal-rebuild.md) функции требуется компилятор для создания и хранения C++ класса сведения о зависимостях, который занимает место на диске. Чтобы сэкономить место на диске, можно использовать `#pragma component( minrebuild, off )` каждый раз, когда не нужно собирать сведения о зависимости, например, в неизменяемых файлах заголовка. Вставить `#pragma component(minrebuild, on)` после неизменяемых классов для включения зависимостей коллекции обратно на.

### <a name="reduce-type-information"></a>Уменьшение сведений о типах

`mintypeinfo` Снижает отладочная информация для определенной области. Эти сведения имеют значительный объем, что влияет на размер PDB- и OBJ-файлов. Невозможно отладить классы и структуры в области параметра mintypeinfo. Использование параметра mintypeinfo поможет избежать следующего предупреждения.

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Дополнительные сведения см. в разделе [/Gm (включение минимального перепостроения)](../build/reference/gm-enable-minimal-rebuild.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)