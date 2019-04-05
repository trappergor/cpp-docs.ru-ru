---
title: component
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: cfb9d2bb9d6ddd2d430c2c031f3c8a51946391b1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032970"
---
# <a name="component"></a>component
Контролирует сбор сведений о просмотре или зависимостях из файлов исходного кода.

## <a name="syntax"></a>Синтаксис

```
#pragma component( browser, { on | off }[, references [, name ]] )
#pragma component( minrebuild, on | off )
#pragma component( mintypeinfo, on | off )
```

## <a name="remarks"></a>Примечания

### <a name="browser"></a>Браузер

Можно включить или отключить сбор информации и задать игнорирование конкретных имен по мере сбора информации.

Включение и отключение сбора информации контролирует сбор сведений о просмотре, начиная с директивы pragma. Пример:

```
#pragma component(browser, off)
```

предотвращает сбор информации о просмотре компилятором.

> [!NOTE]
> Для включения сбора сведений о просмотре с помощью этой директивы #pragma [информацию об исходном коде сначала необходимо включить](../build/reference/building-browse-information-files-overview.md).

`references` Параметр может использоваться с или без *имя* аргумент. С помощью `references` без *имя* включает или выключает сбор ссылок (другие сведения о просмотре прежнему собираются, тем не менее). Пример:

```
#pragma component(browser, off, references)
```

предотвращает сбор информации о ссылках компилятором.

С помощью `references` с *имя* и `off` не позволяет ссылкам на *имя* появлялись в окне сведений о просмотре. Используйте этот синтаксис, чтобы игнорировать ненужные имена и типы, уменьшая тем самым размер файлов со сведениями о просмотре. Пример:

```
#pragma component(browser, off, references, DWORD)
```

игнорирует ссылки на параметр DWORD с этого момента. Вы можете включить сбор ссылок на DWORD снова с помощью `on`:

```
#pragma component(browser, on, references, DWORD)
```

Это единственный способ возобновить сбор ссылок на *имя*; вы должны явно включить все *имя* , вы отключали функцию.

Чтобы предотвратить расширение препроцессор *имя* (например, расширение NULL 0), поместите его в кавычки:

```
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>Минимальная повторная сборка

Возможность минимальной повторной сборки Visual C++ требует, чтобы компилятор создавал и сохранял сведения о зависимости классов C++, что, в свою очередь, занимает место на диске. Чтобы сэкономить место на диске, можно использовать `#pragma component( minrebuild, off )` каждый раз, когда не нужно собирать сведения о зависимости, например, в неизменяемых файлах заголовка. Вставить `#pragma component(minrebuild, on)` после неизменяемых классов для включения зависимостей коллекции обратно на.

### <a name="reduce-type-information"></a>Уменьшение сведений о типах

`mintypeinfo` Снижает отладочная информация для определенной области. Эти сведения имеют значительный объем, что влияет на размер PDB- и OBJ-файлов. Невозможно отладить классы и структуры в области параметра mintypeinfo. Использование параметра mintypeinfo поможет избежать следующего предупреждения.

```
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

Дополнительные сведения см. в разделе [включение минимального перепостроения](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) параметр компилятора.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)