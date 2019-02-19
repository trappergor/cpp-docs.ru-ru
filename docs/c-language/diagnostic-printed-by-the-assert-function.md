---
title: Диагностика, напечатанная функцией assert
ms.date: 11/04/2016
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
ms.openlocfilehash: 666ba22d642b772fe8ad336f57ab1bdd82bd2e18
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151004"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Диагностика, напечатанная функцией assert

**ANSI 4.2** Диагностика, выведенная функцией assert, и поведение завершения функции **assert**

Функция **assert** выводит диагностическое сообщение и вызывает подпрограмму **abort**, если значение выражения — false (0). Диагностическое сообщение имеет форму

> **Assertion failed**: <em>expression</em>**, file** <em>filename</em>**, line** *linenumber*

где *filename* — это имя исходного файла, а *linenumber* — номер строки утверждения, завершившегося сбоем в файле исходного кода. Если *expression* равно true (ненулевое), никакие действия не предпринимаются.

## <a name="see-also"></a>См. также

[Функции библиотеки](../c-language/library-functions.md)
