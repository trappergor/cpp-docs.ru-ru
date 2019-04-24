---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 3f8975ec9737e02bb1216166cc6c241549e95a07
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029373"
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