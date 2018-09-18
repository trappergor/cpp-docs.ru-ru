---
title: Тип для строковых литералов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7773882d6fb04341a6f6d3a2cbcfda1d05f85d17
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063285"
---
# <a name="type-for-string-literals"></a>Тип для строковых литералов

Строковые литералы имеют тип массива `char` (т. е., **char[ ]**). (Строки расширенных символов имеют тип массива `wchar_t` (т. е., **wchar_t []**).) Это означает, что строка является массивом с элементами типа `char`. Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.

## <a name="see-also"></a>См. также

[Строковые литералы в C](../c-language/c-string-literals.md)