---
title: VERSION (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VERSION
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
ms.openlocfilehash: 6d275e1e191e0550143dd5e7a828b734bba0fc96
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414061"
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
