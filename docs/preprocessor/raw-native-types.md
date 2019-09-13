---
title: raw_native_types, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: eb08a8e7cb081bd7a470c3c1ecf1492a7a65f833
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216069"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types, атрибут импорта

**C++Зависящ**

Отключает использование классов поддержки COM в функциях-оболочках высокого уровня и принудительное использование типов данных низкого уровня.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **raw_native_types**

## <a name="remarks"></a>Примечания

По умолчанию методы обработки ошибок высокого уровня используют классы поддержки COM [_bstr_t](../cpp/bstr-t-class.md) и [_variant_t](../cpp/variant-t-class.md) `BSTR` вместо типов данных и `VARIANT` и указателей необработанных COM-интерфейсов. Эти классы инкапсулируют сведения выделения и отмены выделения хранилища памяти для этих типов данных и значительно упрощают операции приведения и преобразования типов.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
