---
title: raw_property_prefixes | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_property_prefixes
dev_langs:
- C++
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1170440428a5c92e383152826827989d602e69fb
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808749"
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