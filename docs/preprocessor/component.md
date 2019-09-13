---
title: Прагма component
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 578c590bdb4223f173e0249c18d0eea4e78a18db
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220479"
---
# <a name="component-pragma"></a>Прагма component

Управляет сбором сведений о просмотре или сведений о зависимостях из исходных файлов.

## <a name="syntax"></a>Синтаксис

> **#pragma компонент (браузер,** { **On** | **Off** } [ **,** **References** [ **,** *Name* ]] **)**  \
> **компонент #pragma (минребуилд,** { **On** | **Off** } **)**  \
> **компонент #pragma (минтипеинфо,** { **On** | **Off** } **)**

## <a name="remarks"></a>Примечания

### <a name="browser"></a>Browser

Можно включить или отключить сбор информации и задать игнорирование конкретных имен по мере сбора информации.

Включение и отключение сбора информации контролирует сбор сведений о просмотре, начиная с директивы pragma. Например:

```cpp
#pragma component(browser, off)
```

предотвращает сбор информации о просмотре компилятором.

> [!NOTE]
> Чтобы включить сбор сведений для просмотра с помощью этой директивы pragma, [необходимо сначала включить сведения о просмотре](../build/reference/building-browse-information-files-overview.md).

Параметр **References** можно использовать с аргументом *Name* или без него. При использовании **ссылок** без *имени* включается или отключается сбор ссылок (другие сведения о просмотре по-другому сохраняются). Например:

```cpp
#pragma component(browser, off, references)
```

предотвращает сбор информации о ссылках компилятором.

Использование **ссылок** с *именем* и **Off** предотвращает отображение ссылок на *имя* в окне просмотра сведений. Используйте этот синтаксис, чтобы игнорировать ненужные имена и типы, уменьшая тем самым размер файлов со сведениями о просмотре. Например:

```cpp
#pragma component(browser, off, references, DWORD)
```

игнорирует ссылки на DWORD с этого момента. Вы можете включить сбор ссылок в DWORD с помощью **On**:

```cpp
#pragma component(browser, on, references, DWORD)
```

Это единственный способ возобновления сбора ссылок на *имя*; необходимо явно включить любое *имя* , которое вы отключили.

Чтобы запретить препроцессору расширение *имени* (например, расширение null до 0), заключите его в кавычки:

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>Минимальное перестроение

Устаревшая функция [/GM (включение минимального перестроения)](../build/reference/gm-enable-minimal-rebuild.md) требует от компилятора создания и хранения C++ сведений о зависимостях класса, что занимает место на диске. Чтобы сэкономить место на диске, можно использовать `#pragma component( minrebuild, off )` каждый раз, когда не требуется выполнять получение сведений о зависимостях, например, в неизменяемых файлах заголовков. Вставьте `#pragma component( minrebuild, on )` после неизменяемых классов, чтобы снова включить сбор зависимостей.

### <a name="reduce-type-information"></a>Сокращение сведений о типах

`mintypeinfo` Параметр сокращает отладочную информацию для указанной области. Эти сведения имеют значительный объем, что влияет на размер PDB- и OBJ-файлов. Невозможно отладить классы и структуры в области параметра mintypeinfo. Использование параметра mintypeinfo поможет избежать следующего предупреждения.

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Дополнительные сведения см. в описании параметра компилятора [/GM (включение минимального перестроения)](../build/reference/gm-enable-minimal-rebuild.md) .

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
