---
title: high_method_prefix
ms.date: 10/18/2018
f1_keywords:
- high_method_prefix
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
ms.openlocfilehash: 1575b2e3fee461ee0e3987aaf1e770d0611e31ec
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028990"
---
# <a name="highmethodprefix"></a>high_method_prefix

**Блок, относящийся только к языку C++**

Задает префикс, используемый при именовании высокоуровневых свойств и методов.

## <a name="syntax"></a>Синтаксис

```
high_method_prefix("Prefix")
```

### <a name="parameters"></a>Параметры

*Префикс*<br/>
Префикс, который следует использовать.

## <a name="remarks"></a>Примечания

По умолчанию высокоуровневые свойства и методы обработки ошибок предоставляются функциями-членами с именами без префикса. Это имена из библиотеки типов.

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)