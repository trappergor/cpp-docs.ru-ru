---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: d6a320089d5954b2cf1d0d96ae1f37656f2ddd58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032392"
---
# <a name="exclude-import"></a>исключить (\#импорт)

**Конкретных C++**

Исключает элементы из создаваемых файлов заголовка библиотеки типов.

## <a name="syntax"></a>Синтаксис

```
exclude("Name1"[, "Name2",...])
```

### <a name="parameters"></a>Параметры

*Name1*<br/>
Первый исключаемый элемент.

*Имя 2*<br/>
Второй исключаемый элемент (при необходимости).

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Этот атрибут может принимать любое количество аргументов, каждый из которых является именем исключаемого элемента, находящегося на верхнем уровне библиотеки типов.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)