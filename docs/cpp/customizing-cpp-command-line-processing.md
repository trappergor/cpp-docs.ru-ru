---
title: Настройка обработки командной строки C++
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
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
ms.openlocfilehash: 1541840521695658b5c4d809ba7e11767b1330a2
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857558"
---
# <a name="customizing-c-command-line-processing"></a>Настройка обработки командной строки C++

**Блок, относящийся только к системам Майкрософт**

Если программа не принимает аргументы командной строки, можно сохранить небольшой объем пространства, подавив использование подпрограммы библиотеки, выполняющей обработку командной строки. Эта подпрограммы называется `_setargv` и описывается в разделе [расширение подстановочных знаков](../cpp/wildcard-expansion.md). Чтобы подавить его использование, определите подпрограммы, которая не выполняет никаких действий в файле, содержащем функцию `main`, и назовите ее `_setargv`. Вызов `_setargv` будет удовлетворен определением `_setargv`, а версия библиотеки не загружается.

Аналогично, если вы никогда не обращаетесь к таблице окружения с помощью аргумента `envp`, можно предоставить собственную пустую подпрограммы, которая будет использоваться вместо `_setenvp`, подпрограммы обработки среды. Как и в случае функции `_setargv`, `_setenvp` должны быть объявлены как **extern "C"** .

Программа может вызывать `spawn` или `exec` семейства подпрограмм в библиотеке времени выполнения C. В этом случае не следует подавлять подпрограмму обработки среды, поскольку она используется для передачи среды из родительского процесса в дочерний процесс.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также:

[Функция main: запуск программы](../cpp/main-program-startup.md)