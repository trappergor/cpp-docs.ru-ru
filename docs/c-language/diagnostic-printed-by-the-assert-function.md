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
ms.openlocfilehash: 1e824e94f79aa01ab3a82675fb3e8f76059c567d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195556"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Диагностика, напечатанная функцией assert
**ANSI 4.2** Диагностика, выведенная функцией assert, и поведение завершения функции **assert**  
  
Функция **assert** выводит диагностическое сообщение и вызывает подпрограмму **abort**, если значение выражения — false (0). Диагностическое сообщение имеет форму  

> **Assertion failed**: <em>expression</em>**, file** <em>filename</em>**, line** *linenumber*  

где *filename* — это имя исходного файла, а *linenumber* — номер строки утверждения, завершившегося сбоем в файле исходного кода. Если *expression* равно true (ненулевое), никакие действия не предпринимаются.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)