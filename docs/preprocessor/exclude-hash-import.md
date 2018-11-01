---
title: exclude (#import)
ms.date: 10/18/2018
f1_keywords:
- exclude
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
ms.openlocfilehash: 1de1376fbe80147bc9fe01ea83bad81912431310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498258"
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