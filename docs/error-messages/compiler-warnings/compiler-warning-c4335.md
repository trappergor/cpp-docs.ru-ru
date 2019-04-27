---
title: Предупреждение компилятора C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: 43c2f5d9092cdbad14e429349bd7d04e236b75e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151855"
---
# <a name="compiler-warning-c4335"></a>Предупреждение компилятора C4335

Обнаружен файл в формате Mac: преобразуйте исходный файл в формат DOS или UNIX

Символ окончания строки в первой строке исходного файла — стиль Macintosh («\r») в отличие от UNIX («\n») или DOS («\r\n»).

Это предупреждение всегда выдается как ошибки.  См. в разделе [предупреждение](../../preprocessor/warning.md) Дополнительные сведения о том, как отключить это предупреждение.  Кроме того это предупреждение при компиляции выдается только один раз. Таким образом при наличии нескольких `#include` директивы, в которых файлы указываются в формате Macintosh, C4335 выдается всего один раз.

Для создания файлов в формате Macintosh рекомендуется с помощью **Дополнительные параметры сохранения** (на **файл** меню) в Visual Studio.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4335.

```
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```