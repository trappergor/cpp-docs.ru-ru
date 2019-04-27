---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: ae79ce9245bb1c0425c3e9b92dd27b52fa443dba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179611"
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