---
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: b1bc536507716e5c117718ec825bf7fe76c84b61
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216142"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++Зависящ**

Указывает другой префикс, чтобы избежать конфликтов имен.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **raw_method_prefix (** "*префикс*" **)**

### <a name="parameters"></a>Параметры

*Prefix*\
Необходимый префикс.

## <a name="remarks"></a>Примечания

Низкоуровневые свойства и методы предоставляются функциями-членами, именуемыми с помощью префикса по умолчанию **raw_** , чтобы избежать конфликтов имен с функциями-членами высокого уровня обработки ошибок.

> [!NOTE]
> Эффекты атрибута **raw_method_prefix** не изменяются при наличии атрибута [raw_interfaces_only](raw-interfaces-only.md) . **Raw_method_prefix** всегда имеет приоритет над `raw_interfaces_only` указанием префикса. Если в одной `#import` инструкции используются оба атрибута, то используется префикс, заданный атрибутом **raw_method_prefix** .

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
