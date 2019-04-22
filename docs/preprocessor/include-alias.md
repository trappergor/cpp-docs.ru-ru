---
title: include_alias
ms.date: 12/16/2018
f1_keywords:
- vc-pragma.include_alias
- include_alias_CPP
helpviewer_keywords:
- pragmas, include_alias
- include_alias pragma
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
ms.openlocfilehash: 187fa94f7c2a5457df655081b87a7f49d38adfa2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024105"
---
# <a name="includealias"></a>include_alias

Указывает, что при *alias_filename* находится в `#include` директив, компилятор заменяет *actual_filename* на его месте.

## <a name="syntax"></a>Синтаксис

> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>Директива #pragma include_alias («*alias_filename*","*actual_filename*")
> #<a name="pragma-includealiasaliasfilename-actualfilename"></a>Директива #pragma include_alias (\<*alias_filename*>, \< *actual_filename*>)

## <a name="remarks"></a>Примечания

**Include_alias** директиву pragma позволяет заменить файлы, имеющие разные имена или путей для имен файлов, включенных в исходные файлы. Например некоторые файловые системы поддерживают длинных именах файлов заголовков, чем системное ограничение для файла FAT 8.3. Компилятор не может просто усечь более длинные имена до этого стандарта, поскольку первые восемь символов в длинных именах файлов заголовков могут быть неуникальными. Когда компилятор встречает *alias_filename* строку, он подставляет *actual_filename*и выполняет поиск файла заголовка *actual_filename* вместо этого. Эта директива pragma должна располагаться до соответствующей директивы `#include`. Пример:

```cpp
// First eight characters of these two files not unique.
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )

#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )

#include "AppleSystemHeaderQuickdraw.h"
#include "AppleSystemHeaderFruit.h"
#include "GraphicsMenu.h"
```

Псевдоним должен точно соответствовать заданному имени как по написанию, так и по регистру. а также по использованию двойных кавычек и угловых скобок. **Include_alias** pragma выполняет сопоставляет строки в имена файлов; проверка имени файла не выполняется. Рассмотрим директивы в следующем примере:

```cpp
#pragma include_alias("mymath.h", "math.h")
#include "./mymath.h"
#include "sys/mymath.h"
```

В этом примере псевдоним не назначается (подстановка не выполняется), поскольку строки файлов заголовков совпадают не полностью. Кроме того, именах файлов заголовков, используемых как аргументы для `/Yu` и `/Yc` параметры компилятора, или `hdrstop` pragma, подстановка не выполняется. Например, представим, что исходный файл содержит следующую директиву:

```cpp
#include <AppleSystemHeaderStop.h>
```

В этом случае должен использоваться следующий параметр компилятора:

> /YcAppleSystemHeaderStop.h

Можно использовать **include_alias** pragma для сопоставления имен файлов заголовка в другой. Пример:

```cpp
#pragma include_alias( "api.h", "c:\version1.0\api.h" )
#pragma include_alias( <stdio.h>, <newstdio.h> )
#include "api.h"
#include <stdio.h>
```

Не смешивайте имена файлов в двойных кавычках с именами файлов, заключенными в угловые скобки. Например, в двух приведенных выше `#pragma include_alias` директивы, компилятор не будет выполнять подстановку для следующих `#include` директивы:

```cpp
#include <api.h>
#include "stdio.h"
```

Кроме того, следующая директива вызовет ошибку:

```cpp
#pragma include_alias(<header.h>, "header.h")  // Error
```

Обратите внимание, что имя файла не сообщали о в сообщениях об ошибках, или в качестве значения из предварительно определенных `__FILE__` макрос, является имя файла, после выполнения подстановки. Например см. в разделе выходных данных после следующие директивы:

```cpp
#pragma include_alias( "VERYLONGFILENAME.H", "myfile.h" )
#include "VERYLONGFILENAME.H"
```

Ошибка в VERYLONGFILENAME. H выдает следующее сообщение об ошибке:

```Output
myfile.h(15) : error C2059 : syntax error
```

Также обратите внимание, что транзитивность не поддерживается. Рассмотрим следующий пример:

```cpp
#pragma include_alias( "one.h", "two.h" )
#pragma include_alias( "two.h", "three.h" )
#include "one.h"
```

Компилятор выполняет поиск файл two.h, а не three.h.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
