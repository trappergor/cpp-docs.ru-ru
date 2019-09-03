---
title: no_auto_exclude, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 530c2b2adf24e964cb0a512371f4430a61bf8b11
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216074"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude, атрибут импорта

**C++Зависящ**

Отключает автоматическое исключение.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_auto_exclude**

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. Директива `#import` пытается предотвратить ошибки об использовании нескольких определений, автоматически исключая такие элементы. Это приводит к тому, что для каждого исключаемого элемента выдается [Предупреждение компилятора (уровень 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) . Вы можете отключить автоматическое исключение с помощью этого атрибута.

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
