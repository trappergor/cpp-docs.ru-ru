---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 26527ca69c66c73f5d41084dc42df5faa34481d3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030545"
---
# <a name="noimplementation"></a>no_implementation
**Блок, относящийся только к языку C++**

Отключает создание заголовка .tli, который содержит реализацию функций-членов оболочки.

## <a name="syntax"></a>Синтаксис

```
no_implementation
```

## <a name="remarks"></a>Примечания

Если этот атрибут указан, то заголовок .tlh с объявлениями для предоставления элементов библиотеки типов создается без оператора `#include` для включения файла заголовка .tli.

Этот атрибут используется в сочетании с [implementation_only](../preprocessor/implementation-only.md).

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)