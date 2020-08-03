---
title: Тип для строковых литералов
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
ms.openlocfilehash: cd84a8c37e2929394e34010d14fc9264080539cc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199000"
---
# <a name="type-for-string-literals"></a>Тип для строковых литералов

Строковые литералы имеют тип массива **`char`** (т. е., **char[ ]** ). (Строки расширенных символов имеют тип массива **`wchar_t`** (т. е., **wchar_t[ ]** ).) Это означает, что строка является массивом с элементами типа **`char`** . Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.

## <a name="see-also"></a>См. также

[Строковые литералы в C](../c-language/c-string-literals.md)
