---
title: "Развертывание знаков подстановки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 779a788cae6523a48a82694e55edf3c1da5519d7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).  
  
 Аргументы командной строки обрабатываются процедурой **_setargv** (или **_wsetargv** в среде Юникода), которая по умолчанию не развертывает знаки подстановки в отдельные строки в `argv`массив строк. Дополнительные сведения о включении подстановочных знаков см. [расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)
