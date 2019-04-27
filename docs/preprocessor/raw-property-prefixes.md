---
title: raw_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 23250b524fdaa2181c8e28229ccec680ffdae715
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179806"
---
# <a name="rawpropertyprefixes"></a>raw_property_prefixes

**Конкретных C++**

Задает другие префиксы для трех методов свойств.

## <a name="syntax"></a>Синтаксис

```
raw_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>Параметры

*GetPrefix*<br/>
Префикс, используемый для `propget` методы.

*PutPrefix*<br/>
Префикс, используемый для `propput` методы.

*PutRefPrefix*<br/>
Префикс, используемый для `propputref` методы.

## <a name="remarks"></a>Примечания

По умолчанию низкоуровневые `propget`, `propput`, и `propputref` методы предоставляются функциями-членами, именами, содержащими префиксы **get_**, **put_**, и **putref_** соответственно. Эти префиксы совместимы с именами, используемыми в файлах заголовков, которые генерирует MIDL.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)