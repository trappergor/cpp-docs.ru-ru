---
title: "Пространство имен stdext | Документы Майкрософт"
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 265a10e71064f2bf3a318a272b751009b1b193be
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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

