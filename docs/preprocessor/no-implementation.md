---
title: no_implementation, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 8f0a7454fdbedc1959b665ccb2a23748d21c342d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220769"
---
# <a name="no_implementation-import-attribute"></a>no_implementation, атрибут импорта

**C++Зависящ**

Подавляет создание `.tli` заголовка, содержащего реализации функций-членов-оболочек.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_implementation**

## <a name="remarks"></a>Примечания

Если этот атрибут указан, то `.tlh` заголовок с объявлениями, которые предоставляют элементы библиотеки типов, будет создан `#include` без инструкции для включения `.tli` файла заголовка.

Этот атрибут используется в сочетании с [implementation_only](../preprocessor/implementation-only.md).

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
