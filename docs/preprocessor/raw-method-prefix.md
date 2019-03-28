---
title: raw_method_prefix
ms.date: 03/27/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: c3015cf8b51646d25fd8f36a7336c63dc8fe492b
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565601"
---
# <a name="rawmethodprefix"></a>raw_method_prefix

**Конкретных C++**

Указывает другой префикс, чтобы избежать конфликтов имен.

## <a name="syntax"></a>Синтаксис

```
raw_method_prefix("Prefix")
```

### <a name="parameters"></a>Параметры

*Prefix*<br/>
Необходимый префикс.

## <a name="remarks"></a>Примечания

Низкоуровневые свойства и методы предоставляются функциями-членами с именами с префиксом по умолчанию **raw_** во избежание конфликтов имен с помощью функции-члены высокого уровня обработки ошибок.

> [!NOTE]
> Последствия **raw_method_prefix** атрибута не изменяется при наличии [raw_interfaces_only](raw-interfaces-only.md) атрибута. **Raw_method_prefix** всегда имеет приоритет над `raw_interfaces_only` в определении префикса. Если оба атрибута используются в том же `#import` инструкции, а затем префикс, определенный параметром **raw_method_prefix** используется атрибут.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)