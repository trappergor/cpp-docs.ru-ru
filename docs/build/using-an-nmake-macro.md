---
title: Использование макроса NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: a5f0fb9b13c5d5647b8f4ee382951df6282e8d68
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415647"
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
