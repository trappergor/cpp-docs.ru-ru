---
title: тлбид, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 364fb224b0f2769cb0933e71d18ff70768189328
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216532"
---
# <a name="tlbid-import-attribute"></a>тлбид, атрибут импорта

**C++Зависящ**

Позволяет загружать библиотеки, отличные от основной библиотеки типов.

## <a name="syntax"></a>Синтаксис

> **#import** *Type-Library-DLL* **тлбид (** *число* **)**

### <a name="parameters"></a>Параметры

*Нумерация*\
Номер библиотеки типов в *Type-Library-DLL*.

## <a name="remarks"></a>Примечания

Если в одну библиотеку DLL встроено несколько библиотек типов, можно загрузить библиотеки, отличные от первичной библиотеки типов, с помощью **тлбид**.

Например:

```cpp
#import <MyResource.dll> tlbid(2)
```

эквивалентно выражению:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
