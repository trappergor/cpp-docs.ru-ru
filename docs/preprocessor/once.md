---
title: Прагма once
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragmas, once
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
ms.openlocfilehash: 643ad83b672f7b632925383972751a966256eb41
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220540"
---
# <a name="once-pragma"></a>Прагма once

Указывает, что компилятор включает файл заголовка только один раз при компиляции файла с исходным кодом.

## <a name="syntax"></a>Синтаксис

> **#pragma один раз**

## <a name="remarks"></a>Примечания

Использование `#pragma once` может сократить время сборки, так как компилятор не будет открывать и считывать файл снова после первого `#include` файла в записи преобразования. Он называется оптимизациейс множественным включением. Он действует аналогично параметру *include guard* , который использует определения макросов препроцессора для предотвращения множественного включения содержимого файла. Это также помогает предотвратить нарушения *одного правила определения*, требование, что все шаблоны, типы, функции и объекты содержат не более одного определения в коде.

Например:

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

Мы рекомендуем директиву `#pragma once` для нового кода, так как она не засоряет глобальное пространство имен символами препроцессора. Она требует меньшего числа символов, менее отвлекается от работы и не может вызвать *конфликты символов*, ошибки, вызванные тем, что в разных файлах заголовков используется тот же символ препроцессора, что и для значения Guard. Он не является частью C++ стандартного, но реализуется с помощью нескольких распространенных компиляторов.

В одном и том же файле нет преимуществ использования как набора условий, `#pragma once` так и того и другого. Компилятор распознает идиому include и реализует оптимизацию с множественным включением таким же образом, как `#pragma once` и директива, если код без комментария или директива препроцессора предшествует стандартной форме идиомы.

```cpp
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

Мы рекомендуем использовать параметр include guard, если код должен быть переносимым на компиляторы, не `#pragma once` реализующие директиву, для поддержания согласованности с существующим кодом или при невозможности оптимизации с несколькими включаемыми данными. Это может произойти в сложных проектах, когда псевдонимы в файловой системе или пути включения псевдонимов не позволяют компилятору идентифицировать идентичные включаемые файлы по каноническому пути.

Будьте внимательны и не `#pragma once` используйте или включите в файлы заголовков параметр include guard, предназначенный для включения в несколько раз, который использует символы препроцессора для управления их эффектами. Пример этой схемы см. в \<разделе файл заголовка Assert. h >. Также будьте внимательны при управлении путями include, чтобы избежать создания нескольких путей к включенным файлам, что может привести к невозможности одновременной `#pragma once`оптимизации нескольких включаемых файлов.

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
