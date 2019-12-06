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
ms.openlocfilehash: 1fdea297bb45a06a08bde4f63f90eabef6ddb539
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857181"
---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки

**Блок, относящийся только к системам Майкрософт**

Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).

Аргументы командной строки обрабатываются с помощью подпрограммы, именуемой `_setargv` (или `_wsetargv` в среде расширенных символов), которая по умолчанию не расширяет подстановочные знаки в отдельные строки в `argv` массиве строк. Дополнительные сведения о включении расширения с подстановочными знаками см. в разделе [расширение аргументов-шаблонов](../c-language/expanding-wildcard-arguments.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Функция main: запуск программы](../cpp/main-program-startup.md)