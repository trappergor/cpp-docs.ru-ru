---
title: Настройка обработки командной строки C++ | Документы Microsoft
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
ms.openlocfilehash: 1e2691ba3b83cd536c6f0a152bf4de2a855f81e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411115"
---
# <a name="customizing-c-command-line-processing"></a>Настройка обработки командной строки C++
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Если программа не принимает аргументы командной строки, можно сохранить небольшой объем пространства, подавив использование подпрограммы библиотеки, выполняющей обработку командной строки. Эта подпрограмма называется **_setargv** и рассматривается в [подстановочных знаков в](../cpp/wildcard-expansion.md). Чтобы подавить ее использование, определите подпрограмму, которая не выполняет никаких действий в файле, содержащем **основной** и назовите ее **_setargv**. Вызов **_setargv** будет удовлетворен определением **_setargv**, и версия библиотеки не будет загружена.  
  
 Аналогично Если вы никогда не получить доступ к таблице среды через `envp` аргумент, можно предоставить собственную пустую подпрограмму для использования вместо **_setenvp**, подпрограмму обработки среды. Как и в случае с **_setargv** функции **_setenvp** должен быть объявлен как **extern «C»**.  
  
 Приложение может вызывать **spawn** или `exec` семейство подпрограмм в библиотеке времени выполнения C. В этом случае не следует подавлять подпрограмму обработки среды, поскольку она используется для передачи среды из родительского процесса в дочерний процесс.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)