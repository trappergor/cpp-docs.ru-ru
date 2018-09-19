---
title: ВЕРСИЯ (C/C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VERSION
dev_langs:
- C++
helpviewer_keywords:
- VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7330d979e841d952f7e800e52ae762256ede6808
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718306"
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