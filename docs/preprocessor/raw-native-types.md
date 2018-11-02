---
title: raw_native_types
ms.date: 11/04/2016
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: e48aa2ca1469d38b67dcb06a3377713141a158e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620445"
---
# <a name="rawnativetypes"></a>raw_native_types
**Конкретных C++**

Отключает использование классов поддержки COM в высокоуровневых функциях оболочки и принудительно использует вместо них низкоуровневые типы данных.

## <a name="syntax"></a>Синтаксис

```
raw_native_types
```

## <a name="remarks"></a>Примечания

По умолчанию высокоуровневые методы обработки ошибок используют классы с поддержкой COM [_bstr_t](../cpp/bstr-t-class.md) и [_variant_t](../cpp/variant-t-class.md) вместо `BSTR` и `VARIANT` типов данных и необработанные COM указателей на интерфейс. Эти классы инкапсулируют сведения выделения и отмены выделения хранилища памяти для этих типов данных и значительно упрощают операции приведения и преобразования типов.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)