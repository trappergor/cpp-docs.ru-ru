---
title: "Настройка обработки командной строки C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 977ab6f5a7a8dbddf045e83a14127ac979a114a9
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="customizing-c-command-line-processing"></a>Настройка обработки командной строки C++
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Если программа не принимает аргументы командной строки, можно сохранить небольшой объем пространства, подавив использование подпрограммы библиотеки, выполняющей обработку командной строки. Эта подпрограмма называется **_setargv** и рассматривается в [подстановочных знаков в](../cpp/wildcard-expansion.md). Чтобы подавить ее использование, определите подпрограмму, которая не выполняет никаких действий в файле, содержащем **основной** и назовите ее **_setargv**. Вызов **_setargv** будет удовлетворен определением **_setargv**, и версия библиотеки не будет загружена.  
  
 Аналогично Если вы никогда не получить доступ к таблице среды через `envp` аргумент, можно предоставить собственную пустую подпрограмму для использования вместо **_setenvp**, подпрограмму обработки среды. Как и в случае с **_setargv** функции **_setenvp** должен быть объявлен как **extern «C»**.  
  
 Приложение может вызывать **spawn** или `exec` семейство подпрограмм в библиотеке времени выполнения C. В этом случае не следует подавлять подпрограмму обработки среды, поскольку она используется для передачи среды из родительского процесса в дочерний процесс.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Функция main: запуск программы](../cpp/main-program-startup.md)
