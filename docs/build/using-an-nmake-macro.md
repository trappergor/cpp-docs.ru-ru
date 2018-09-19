---
title: Использование макроса NMAKE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0b68a5f3128b5d3780895f8080411819ed9b538
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712599"
---
# <a name="using-an-nmake-macro"></a>Использование макроса NMAKE

Чтобы использовать макрос, имя необходимо заключите в круглые скобки, предшествует знак доллара ($), как показано ниже.

## <a name="syntax"></a>Синтаксис

```
$(macroname)
```

## <a name="remarks"></a>Примечания

Пробелы не допускаются. Круглые скобки необязательны Если *имя макроса* — это отдельный символ. Строка определения заменяет $(*имя макроса*); неопределенный макрос заменяется на пустую строку.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

[Макроподстановка](../build/macro-substitution.md)

## <a name="see-also"></a>См. также

[Макросы и программа NMAKE](../build/macros-and-nmake.md)