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
ms.openlocfilehash: 2c219669d018dc8c4cb038e90dffd1137877f422
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382881"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Диагностика, напечатанная функцией assert
**ANSI 4.2** Диагностика, выведенная функцией assert, и поведение завершения функции **assert**  
  
 Функция **assert** выводит диагностическое сообщение и вызывает подпрограмму **abort**, если значение выражения — false (0). Диагностическое сообщение имеет форму  
  
 **Assertion failed**: *expression***, file** *filename***, line** *linenumber*  
  
 где имя файла — это имя файла исходного кода, а номер строки — это номер строки утверждения, завершившегося сбоем в файле исходного кода. Если выражение равно true (ненулевое), никакие действия не предпринимаются.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)