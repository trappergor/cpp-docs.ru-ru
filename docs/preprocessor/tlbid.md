---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 31b71f7c195a7e2ee649b40197551e4ff5efda2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584522"
---
# <a name="tlbid"></a>tlbid

**Конкретных C++**

Позволяет загружать библиотеки, отличные от основной библиотеки типов.

## <a name="syntax"></a>Синтаксис

```
tlbid(number)
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Номер библиотеки типов в файле с именем `filename`.

## <a name="remarks"></a>Примечания

Если несколько библиотек типов встроены в одной библиотеки DLL, можно загружать библиотеки, отличные от основной библиотеки типов с помощью **tlbid**.

Пример:

```cpp
#import <MyResource.dll> tlbid(2)
```

эквивалентно выражению:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)