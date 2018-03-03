---
title: "Распространение компонентов с использованием модулей слияния | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 093c732563844b14a3f99662150d4db9b2fac1fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>Распространение компонентов с использованием модулей слияния
Visual Studio включает [модули слияния](http://msdn.microsoft.com/library/aa367434) для каждого компонента Visual C++, которая лицензирована для распространения вместе с приложением. Если модуль слияния компилируется в файле установщика Windows, он включает развертывание определенных DLL на компьютерах, имеющих определенную платформу. В файле установки укажите, что модули слияния являются необходимыми компонентами для вашего приложения. При установке Visual Studio, модули слияния устанавливаются в \Program Files\Common модули Files\Merge\\. (Только неотладочные версии библиотек DLL Visual C++ могут распространяться.) Дополнительные сведения и ссылка на список модулей слияния, которые лицензируются для распространения см. в разделе [распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md).  
  
 Модули слияния можно использовать для включения возможности установки распространяемых библиотек DLL Visual C++ в папку %SYSTEMROOT%\system32\. (Этот метод использует visual Studio.) Однако установка в эту папку завершится неудачей, если у выполняющего установку пользователя нет прав администратора.  
  
 Рекомендуется не использовать модули слияния за исключением тех случаев, когда нет необходимости обслуживания приложения и нет зависимостей от более чем одной версии библиотек DLL. Модули слияния для разных версий одной и той же библиотеки DLL нельзя включить в один установщик, и модули слияния осложняют поддержку DLL независимо от приложения. Вместо этого рекомендуется установить распространяемый пакет Visual C++.  
  
## <a name="see-also"></a>См. также  
 [Распространение файлов Visual C++](../ide/redistributing-visual-cpp-files.md)