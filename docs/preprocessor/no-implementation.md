---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: d4e55d06bef823d28c5deb3467654bc530a3853e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456788"
---
# <a name="noimplementation"></a>no_implementation
**Конкретных C++**

Отключает создание заголовка .tli, который содержит реализацию функций-членов оболочки.

## <a name="syntax"></a>Синтаксис

```
no_implementation
```

## <a name="remarks"></a>Примечания

Если этот атрибут указан, то заголовок .tlh с объявлениями для предоставления элементов библиотеки типов создается без оператора `#include` для включения файла заголовка .tli.

Этот атрибут используется в сочетании с [implementation_only](../preprocessor/implementation-only.md).

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)