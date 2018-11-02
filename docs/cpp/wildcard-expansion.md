---
title: Развертывание знаков подстановки
ms.date: 11/04/2016
f1_keywords:
- _setargv
helpviewer_keywords:
- asterisk wildcard
- _setargv function
- command line [C++], processing arguments
- command line [C++], wildcards
- command-line wildcards
- question mark, wildcard
ms.assetid: 1a543398-607b-4404-93d1-45d290bde638
ms.openlocfilehash: 2d495f94f2e3fb7b88d235edc7b98f8e90775393
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507440"
---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).

Аргументы командной строки обрабатываются процедурой `_setargv` (или `_wsetargv` в среде Юникода), который по умолчанию не разворачивает подстановочные знаки, в отдельные строки в `argv` массив строк. Дополнительные сведения о включении развертывание знаков подстановки, см. [расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)