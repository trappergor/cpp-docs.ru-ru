---
title: "Предупреждение средств компоновщика LNK4210 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 127d4bdc85d07468f91656bc0aff5f4f2d015df5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4210"></a>Предупреждение средств компоновщика LNK4210
раздел "раздел" существует; могут иметься не обработанные статические инициализаторы или знаки завершения  
  
 Код ввел статические инициализаторы или знаки завершения, но CRT или аналог (требующий их выполнения статические инициализаторы или знаки завершения) не выполняется при запуске приложения. Примеры кода, вызывающего предупреждение:  
  
-   Глобальная переменная класса с помощью конструктора, деструктора или таблицу виртуальных функций.  
  
-   Глобальная переменная, инициализированная с константой без компиляции.  
  
 Чтобы устранить эту проблему, попробуйте один из следующих:  
  
-   Удалите весь код, содержащий статические инициализаторы.  
  
-   Не используйте [/NOENTRY](../../build/reference/noentry-no-entry-point.md).  После удаления/NOENTRY также может потребоваться добавить msvcrt.lib, libcmt.lib или библиотеки libcmtd.lib в командной строке компоновщика.  
  
-   Добавьте msvcrt.lib, libcmt.lib или библиотеки libcmtd.lib в командной строке компоновщика.  
  
-   При переходе с/CLR: pure компиляции/CLR, удалите [/Entry](../../build/reference/entry-entry-point-symbol.md) из строки компоновщика. Это обеспечит инициализацию CRT и позволит статические инициализаторы при запуске приложения.  
  
-   Если проект создается с [/Entry](../../build/reference/entry-entry-point-symbol.md), и если/ENTRY передал функцию, отличного от `_DllMainCRTStartup`, функция должна вызвать CRT_INIT. В разделе [поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md) и статьи базы знаний Q94248, [http://support.microsoft.com/default.aspx?scid=kb;en-us;94248](http://support.microsoft.com/default.aspx?scid=kb;en-us;94248) для получения дополнительной информации.  
  
 [/GS](../../build/reference/gs-buffer-security-check.md) параметр компилятора требует код запуска CRT.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
