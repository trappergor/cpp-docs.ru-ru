---
title: Диагностические сведения, выводимые функцией assert | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac5473a2dd592bbd9af2f65044d3d7d97515dc37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103390"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Диагностика, напечатанная функцией assert

**ANSI 4.2** Диагностика, выведенная функцией assert, и поведение завершения функции **assert**

Функция **assert** выводит диагностическое сообщение и вызывает подпрограмму **abort**, если значение выражения — false (0). Диагностическое сообщение имеет форму

> **Assertion failed**: <em>expression</em>**, file** <em>filename</em>**, line** *linenumber*

где *filename* — это имя исходного файла, а *linenumber* — номер строки утверждения, завершившегося сбоем в файле исходного кода. Если *expression* равно true (ненулевое), никакие действия не предпринимаются.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)