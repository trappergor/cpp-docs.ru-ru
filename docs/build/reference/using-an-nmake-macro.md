---
title: Использование макроса NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: fb3b154ba8b30bbfc9a6c7c6b37720e5c60d6327
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827423"
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

[Макроподстановка](macro-substitution.md)

## <a name="see-also"></a>См. также

[Макросы и программа NMAKE](macros-and-nmake.md)
