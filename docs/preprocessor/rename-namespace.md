---
title: rename_namespace, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: d319d7390e7c7dce070a35be44aad37c7a34e1a0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216657"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace, атрибут импорта

**C++Зависящ**

Переименовывает пространство имен, к которому относится содержимое библиотеки типов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **rename_namespace (** "*новое_имя*" **)**

### <a name="parameters"></a>Параметры

*NewName*\
Новое имя пространства имен.

## <a name="remarks"></a>Примечания

Атрибут **rename_namespace** принимает один аргумент — *newname*, который указывает новое имя для пространства имен.

Чтобы удалить пространство имен, используйте вместо него атрибут [no_namespace](../preprocessor/no-namespace.md) .

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
