---
title: Предупреждение компилятора C4335 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2b28909d0c4b663fffeacbec58ad694131bb008
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036583"
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