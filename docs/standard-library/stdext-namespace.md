---
title: Пространство имен stdext
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: d40f3f7a99db72784cc9a32a9c37064228597d34
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412427"
---
# <a name="stdext-namespace"></a>Пространство имен stdext

Членами [ \<hash_map >](../standard-library/hash-map.md) и [ \<hash_set >](../standard-library/hash-set.md) файлы заголовков не входят в настоящее время ISO C++ standard. Поэтому эти типы и члены были перемещены из пространства имен `std` в пространство имен `stdext`в целях поддержания соответствия стандарту C++.

При компиляции с параметром [/Ze](../build/reference/za-ze-disable-language-extensions.md), который используется по умолчанию, компилятор выдает предупреждение об использовании `std` членами \<hash_map > и \<hash_set > файлы заголовков. Для отключения этого предупреждения используется директива pragma [warning](../preprocessor/warning.md) .

Чтобы компилятор создает ошибку для использования `std` членами \<hash_map > и \<hash_set > файлы заголовков с **/Ze**, добавьте следующую директиву перед `#include` любой C++ файлы заголовков стандартной библиотеки.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

При компиляции с параметром **/Za**, компилятор выдает ошибку.

## <a name="see-also"></a>См. также

[Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)
