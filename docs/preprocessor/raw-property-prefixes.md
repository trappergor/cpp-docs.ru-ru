---
title: raw_property_prefixes, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: d4d91470781e7c5f673fd228c24904322d1db8b3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216042"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes, атрибут импорта

**C++Зависящ**

Задает другие префиксы для трех методов свойств.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **raw_property_prefixes (** "*префикс*" **,** "*путпрефикс*" **,** "*путрефпрефикс*" **)**

### <a name="parameters"></a>Параметры

*Префикс*\
Префикс, используемый для `propget` методов.

*путпрефикс*\
Префикс, используемый для `propput` методов.

*путрефпрефикс*\
Префикс, используемый для `propputref` методов.

## <a name="remarks"></a>Примечания

По умолчанию методы низкого уровня `propget`, `propput`и `propputref` предоставляются функциями-членами с именем с помощью префиксов `get_`, `put_`и `putref_`соответственно. Эти префиксы совместимы с именами, используемыми в файлах заголовков, которые генерирует MIDL.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
