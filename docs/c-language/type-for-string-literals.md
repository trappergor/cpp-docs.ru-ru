---
title: Тип для строковых литералов
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
ms.openlocfilehash: 7e832ac7aa08ad80ab395baa59eabbabb486b46f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344854"
---
# <a name="type-for-string-literals"></a>Тип для строковых литералов

Строковые литералы имеют тип массива `char` (т. е., **char[ ]** ). (Строки расширенных символов имеют тип массива `wchar_t` (т. е., **wchar_t []** ).) Это означает, что строка является массивом с элементами типа `char`. Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.

## <a name="see-also"></a>См. также

[Строковые литералы в C](../c-language/c-string-literals.md)
