---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: ae79ce9245bb1c0425c3e9b92dd27b52fa443dba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037945"
---
# <a name="tlbid"></a>tlbid

**Блок, относящийся только к языку C++**

Позволяет загружать библиотеки, отличные от основной библиотеки типов.

## <a name="syntax"></a>Синтаксис

```
tlbid(number)
```

### <a name="parameters"></a>Параметры

*number*<br/>
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

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)