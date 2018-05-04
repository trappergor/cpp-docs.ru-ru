---
title: Развертывание знаков подстановки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb58d5da479d686cac0d18c9d36e500bd6b5a632
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).  
  
 Аргументы командной строки обрабатываются процедурой **_setargv** (или **_wsetargv** в среде Юникода), которая по умолчанию не развертывает знаки подстановки в отдельные строки в `argv`массив строк. Дополнительные сведения о включении подстановочных знаков см. [расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)