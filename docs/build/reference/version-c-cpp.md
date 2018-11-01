---
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 98758da627390ba4c7e852905457527a343baccc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667380"
---
# <a name="version-cc"></a>VERSION (C/C++)

Указывает ССЫЛКУ, чтобы поместить номер в заголовке файла .exe или DLL.

```
VERSION major[.minor]
```

## <a name="remarks"></a>Примечания

*Основных* и *незначительные* аргументами являются десятичные числа в диапазоне от 0 до 65 535. По умолчанию используется версия 0.0.

Эквивалентный способ указать номер версии — с помощью [сведения о версии](../../build/reference/version-version-information.md) (/ версии) параметр.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)