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
ms.openlocfilehash: cac6b61176b1559ea5810dc061638642926b3969
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077078"
---
# <a name="wildcard-expansion"></a>Развертывание знаков подстановки

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Задавать имена файлов и пути к ним в аргументах командной строки можно при помощи знаков подстановки — вопросительного знака (?) и звездочки (*).

Аргументы командной строки обрабатываются процедурой `_setargv` (или `_wsetargv` в среде Юникода), который по умолчанию не разворачивает подстановочные знаки, в отдельные строки в `argv` массив строк. Дополнительные сведения о включении развертывание знаков подстановки, см. [расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)