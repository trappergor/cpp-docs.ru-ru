---
title: '&lt;typeindex&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <typeindex>
dev_langs:
- C++
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 189fb7cd3757a3f71a50badc682b7b4db611b4e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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
