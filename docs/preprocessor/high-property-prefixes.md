---
title: high_property_prefixes, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 9e44f6f1afae479f803f4c6d866ef3ee38744561
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219003"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes, атрибут импорта

**C++Зависящ**

Задает другие префиксы для трех методов свойств.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **high_property_prefixes (** "*префикс*" **,** "*путпрефикс*" **,** "*путрефпрефикс*" **)**

### <a name="parameters"></a>Параметры

*Префикс*\
Префикс, который будет использоваться для `propget` методов.

*путпрефикс*\
Префикс, который будет использоваться для `propput` методов.

*путрефпрефикс*\
Префикс, который будет использоваться для `propputref` методов.

## <a name="remarks"></a>Примечания

По умолчанию высокоуровневые `propget`методы обработки ошибок, `propput`и `propputref` предоставляются функциями-членами с префиксами `Get`, `Put`и `PutRef`соответственно.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
