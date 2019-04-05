---
title: raw_method_prefix
ms.date: 03/27/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 963e04752dcb797343550d9b89f778bfe0e8a593
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59021415"
---
# <a name="rawmethodprefix"></a>raw_method_prefix

**Блок, относящийся только к языку C++**

Указывает другой префикс, чтобы избежать конфликтов имен.

## <a name="syntax"></a>Синтаксис

```
raw_method_prefix("Prefix")
```

### <a name="parameters"></a>Параметры

*Префикс*<br/>
Необходимый префикс.

## <a name="remarks"></a>Примечания

Низкоуровневые свойства и методы предоставляются функциями-членами с именами с префиксом по умолчанию **raw_** во избежание конфликтов имен с помощью функции-члены высокого уровня обработки ошибок.

> [!NOTE]
> Последствия **raw_method_prefix** атрибута не изменяется при наличии [raw_interfaces_only](raw-interfaces-only.md) атрибута. **Raw_method_prefix** всегда имеет приоритет над `raw_interfaces_only` в определении префикса. Если оба атрибута используются в том же `#import` инструкции, а затем префикс, определенный параметром **raw_method_prefix** используется атрибут.

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)