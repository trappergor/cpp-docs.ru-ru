---
title: no_auto_exclude
ms.date: 11/04/2016
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 04e3b261e24bbe9870a6d3fc428cd68e8c1a8132
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537635"
---
# <a name="noautoexclude"></a>no_auto_exclude
**Конкретных C++**

Отключает автоматическое исключение.

## <a name="syntax"></a>Синтаксис

```
no_auto_exclude
```

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы. Если это сделано, [Предупреждение компилятора (уровень 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) будут выдаваться для каждого элемента, должны быть исключены. Отменить такое автоматическое исключение можно при помощи данного атрибута.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)