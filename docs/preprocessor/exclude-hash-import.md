---
title: исключить (#import) | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- exclude
dev_langs:
- C++
helpviewer_keywords:
- exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c345d9268f63a714eeae4beff78a7ac39ce545a1
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807904"
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