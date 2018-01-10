---
title: "Предупреждение средств компоновщика LNK4210 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4210
dev_langs: C++
helpviewer_keywords: LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4e2d596527b60735b42fb4edfff6f36d0be808d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4210"></a>Предупреждение средств компоновщика LNK4210  
  
> раздел *раздел* существует; могут иметься не обработанные статические инициализаторы или знаки завершения  
  
Часть кода внес статические инициализаторы или знаки завершения, но код запуска библиотеки VCRuntime или его эквивалент (который должен выполнить статические инициализаторы или знаки завершения) не выполняется при запуске приложения. Ниже приведены некоторые примеры кода, который требует статические инициализаторы или знаки завершения.  
  
-   Глобальная переменная класса с конструктором, деструктором или таблицу виртуальных функций.  
  
-   Глобальная переменная инициализируется с константой компиляции времени.  
  
Чтобы устранить эту проблему, попробуйте один из следующих:  
  
-   Удалите весь код, содержащий статические инициализаторы.  
  
-   Не используйте [/NOENTRY](../../build/reference/noentry-no-entry-point.md). После удаления/NOENTRY также может потребоваться удалить [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) командной строки компоновщика.  
  
-   Если сборка использует/MT, добавьте в командной строке компоновщика libcmt.lib, libvcruntime.lib и libucrt.lib. Если сборка использует/MTd, добавьте libcmtd.lib, vcruntimed.lib и libucrtd.lib.  
  
-   При перемещении с параметром/clr: pure компиляции в/CLR, удалите [/Entry](../../build/reference/entry-entry-point-symbol.md) из строки компоновщика. Это позволяет инициализацию CRT и статических инициализаторов, для выполнения при запуске приложения.  
  
 [/GS](../../build/reference/gs-buffer-security-check.md) параметра компилятора требуется инициализация по `__security_init_cookie` функции. Инициализация предоставляется по умолчанию в код запуска библиотеки VCRuntime, работающего в `_DllMainCRTStartup`.  
  
-   Если проект строится с помощью/Entry, и если/ENTRY передал функцию, отличный от `_DllMainCRTStartup`, необходимо вызвать функцию `_CRT_INIT` для инициализации CRT. Если библиотека DLL использует/GS, требуются статические инициализаторы или вызывается в контексте кода MFC или ATL, этот вызов сама по себе недостаточно. В разделе [библиотек DLL и Visual C++ поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)