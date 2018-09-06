---
title: Макроподстановка | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f71ef2e1a8f337a4cd415169b6f9d817042f19a
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894399"
---
# <a name="macro-substitution"></a>Макроподстановка

Когда *имя макроса* вызывается, каждое вхождение *string1* в своем определении строка заменяется *string2*.

## <a name="syntax"></a>Синтаксис

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Примечания

Макроподстановка чувствительно к регистру и буквально; *string1* и *string2* нельзя вызывать макросы. Подстановка не изменяет исходное определение. Можно заменить текст в любой предопределенный макрос, за исключением [ $$@ ](../build/filename-macros.md).

Пробелы или вкладки перед двоеточием; любой после двоеточия, интерпретируется как литерал. Если *string2* имеет значение null, все вхождения *string1* удаляются из строки определения макроса.

## <a name="see-also"></a>См. также

[Использование макроса NMAKE](../build/using-an-nmake-macro.md)