---
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: e22ce63c01185112ed512217156470e6f2948cd5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566625"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

Включите стандартный заголовок \<typeindex>, чтобы определить класс и функцию, которые поддерживают индексацию объектов класса [type_info](../cpp/type-info-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
#include <typeindex>
```

## <a name="remarks"></a>Примечания

[Структура hash](../standard-library/hash-structure.md) определяет `hash function` для сопоставления значений типа [type_index](../standard-library/type-index-class.md) распределению значений индекса.

Класс `type_index` оборачивает указатель в объект `type_info` для индексирования.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
