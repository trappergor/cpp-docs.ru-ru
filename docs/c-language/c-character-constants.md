---
title: Константы символов в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9908bfd8be662a53727e9c833626f329dd45c04
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038585"
---
# <a name="c-character-constants"></a>Константы символов в C

"Константа символа" создается путем заключения одного символа из набора представимых символов в одинарные кавычки (**' '**). Константы символов используются для представления символов в [кодировке выполнения](../c-language/execution-character-set.md).

## <a name="syntax"></a>Синтаксис

*character-constant*: **'** *c-char-sequence* **'**

**L'** *c-char-sequence* **'**

*c-char-sequence*: *c-char*

*c-char-sequence c-char*

*c-char*: любой член исходной кодировки, кроме одинарной кавычки (**'**), обратной косой черты (**\\**) и символа новой строки

*escape-sequence*

*escape-sequence*: *simple-escape-sequence*

*octal-escape-sequence*

*hexadecimal-escape-sequence*

*simple-escape-sequence*: один из символов: **\a \b \f \n \r \t \v**

**\\' \\" \\\ \\?**

*octal-escape-sequence*: **\\**  *octal-digit*

**\\**  *octal-digit octal-digit*

**\\**  *octal-digit octal-digit octal-digit*

*hexadecimal-escape-sequence*: **\x**  *hexadecimal-digit*

*hexadecimal-escape-sequence hexadecimal-digit*

## <a name="see-also"></a>См. также

[Константы в C](../c-language/c-constants.md)