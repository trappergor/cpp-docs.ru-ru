---
title: Значимые символы при внешней компоновке | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6f3b7e26-3fb0-4975-a95d-23a2072c1186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df3c07a172c02e0ea095dbcea9d291235453ca25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035179"
---
# <a name="significant-characters-with-external-linkage"></a>Значимые символы с внешней компоновкой

**ANSI 3.1.2** Число значимых символов при использовании внешней компоновки

Идентификаторы, объявленные `extern` в программах, которые скомпилированы с использованием языка Microsoft C, являются значимыми до 247 символов. Это значение по умолчанию можно изменить на меньшее число, воспользовавшись параметром /H (ограничивает длину внешних имен).

## <a name="see-also"></a>См. также

[Использование ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)