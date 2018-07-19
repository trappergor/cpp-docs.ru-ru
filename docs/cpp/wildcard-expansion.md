---
title: Развертывание знаков подстановки | Документация Майкрософт
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
ms.openlocfilehash: 7f4de54cbbe978534a42dcb9cbfa677eb1597aa5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939140"
---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).  
  
 Аргументы командной строки обрабатываются процедурой `_setargv` (или `_wsetargv` в среде Юникода), который по умолчанию не разворачивает подстановочные знаки, в отдельные строки в `argv` массив строк. Дополнительные сведения о включении развертывание знаков подстановки, см. [расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)