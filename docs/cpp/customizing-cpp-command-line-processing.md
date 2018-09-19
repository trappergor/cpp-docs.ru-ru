---
title: Настройка обработки командной строки C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 855562b8b6eb5e577914fc6305668ee7305c86e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110683"
---
# <a name="customizing-c-command-line-processing"></a>Настройка обработки командной строки C++

## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft

Если программа не принимает аргументы командной строки, можно сохранить небольшой объем пространства, подавив использование подпрограммы библиотеки, выполняющей обработку командной строки. Эта подпрограмма называется `_setargv` и описан в [развертывание знаков подстановки](../cpp/wildcard-expansion.md). Чтобы подавить ее использование, определите подпрограмму, которая не выполняет никаких действий в файле, содержащем `main` функции и назовите его `_setargv`. Вызов `_setargv` будет удовлетворен определением `_setargv`, и версия библиотеки не загружена.

Аналогично Если вы никогда не получить доступ к таблице окружения с помощью `envp` аргумент, можно предоставить собственную пустую подпрограмму для использования вместо `_setenvp`, подпрограмму обработки среды. Так же как `_setargv` функции `_setenvp` должен быть объявлен как **extern «C»**.

Программа может вызывать `spawn` или `exec` семейство подпрограмм в библиотеке времени выполнения C. В этом случае не следует подавлять подпрограмму обработки среды, поскольку она используется для передачи среды из родительского процесса в дочерний процесс.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)