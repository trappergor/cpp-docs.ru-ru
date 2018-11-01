---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 130d19f275612e153955ae49f299fe2f36d098bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579820"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**Конкретных C++**

Задает другие префиксы для трех методов свойств.

## <a name="syntax"></a>Синтаксис

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Параметры

*GetPrefix*<br/>
Префикс, используемый для `propget` методы.

*PutPrefix*<br/>
Префикс, используемый для `propput` методы.

*PutRefPrefix*<br/>
Префикс, используемый для `propputref` методы.

## <a name="remarks"></a>Примечания

По умолчанию высокоуровневые обработки ошибок `propget`, `propput`, и `propputref` методы предоставляются функциями-членами, префиксы `Get`, `Put`, и `PutRef`, соответственно.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)