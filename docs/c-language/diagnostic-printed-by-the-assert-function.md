---
title: Диагностика, напечатанная функцией assert
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 330c694b53957cab2e44da7cb8b52031c33fb5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549049"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Диагностика, напечатанная функцией assert

**ANSI 4.2** Диагностика, выведенная функцией assert, и поведение завершения функции **assert**

Функция **assert** выводит диагностическое сообщение и вызывает подпрограмму **abort**, если значение выражения — false (0). Диагностическое сообщение имеет форму

> **Assertion failed**: <em>expression</em>**, file** <em>filename</em>**, line** *linenumber*

где *filename* — это имя исходного файла, а *linenumber* — номер строки утверждения, завершившегося сбоем в файле исходного кода. Если *expression* равно true (ненулевое), никакие действия не предпринимаются.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)