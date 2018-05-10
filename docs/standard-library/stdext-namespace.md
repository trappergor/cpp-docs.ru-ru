---
title: Пространство имен stdext | Документы Майкрософт
ms.custom: ''
ms.date: 09/06/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 302d5b696a3413e36dd76cb931556a3fae7e7615
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="stdext-namespace"></a>Пространство имен stdext

Члены [ \<hash_map >](../standard-library/hash-map.md) и [ \<hash_set >](../standard-library/hash-set.md) файлы заголовков не в настоящее время являются частью стандарта ISO C++. Поэтому эти типы и члены были перемещены из пространства имен `std` в пространство имен `stdext`в целях поддержания соответствия стандарту C++.

При компиляции с параметром [/Ze](../build/reference/za-ze-disable-language-extensions.md), которое используется по умолчанию, компилятор выдает предупреждение об использовании `std` для членов \<hash_map > и \<hash_set > файлы заголовков. Для отключения этого предупреждения используется директива pragma [warning](../preprocessor/warning.md) .

Чтобы компилятор выдавал ошибку для использования `std` для членов \<hash_map > и \<hash_set > файлы заголовков с **/Ze**, добавьте следующую директиву перед `#include` все файлы заголовков стандартной библиотеки C++.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

При компиляции с параметром **/Za**, компилятор создает ошибку.

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)

