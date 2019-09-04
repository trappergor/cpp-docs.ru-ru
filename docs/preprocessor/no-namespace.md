---
title: no_namespace, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: ba52aed69cdbb46c135e6de5078d718e93f99c87
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220736"
---
# <a name="no_namespace-import-attribute"></a>no_namespace, атрибут импорта

**C++Зависящ**

Указывает, что компилятор не создает имя пространства имен.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_namespace**

## <a name="remarks"></a>Примечания

Содержимое библиотеки типов в файле заголовка `#import` обычно определяется в пространстве имен. Имя пространства имен указывается в `library` инструкции исходного IDL-файла. Если указан атрибут **no_namespace** , компилятор не создает это пространство имен.

Если вы хотите использовать другое имя пространства имен, используйте вместо него атрибут [rename_namespace](../preprocessor/rename-namespace.md) .

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
