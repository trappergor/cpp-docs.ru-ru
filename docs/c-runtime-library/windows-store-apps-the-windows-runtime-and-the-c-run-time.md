---
title: "Приложения для Магазина Windows, среда выполнения Windows и среда выполнения C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 0eb057f9d229c659f339f996d1ff38f65fd2e018
ms.openlocfilehash: fc0ed4b45e04357fae46fb1391d55d184440f12d
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="windows-store-apps-the-windows-runtime-and-the-c-run-time"></a>Приложения для Магазина Windows, среда выполнения Windows и среда выполнения C
Приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] представляют собой программы, исполняемые в среде выполнения Windows, которая выполняется в [!INCLUDE[win8](../build/reference/includes/win8_md.md)].  Среда выполнения Windows — это надежное окружение, контролирующее функции, переменные и ресурсы, доступные приложению [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]. Конструктивные ограничения среды выполнения Windows не позволяют использовать в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] большинство возможностей библиотеки времени выполнения C (CRT).  
  
 Среда выполнения Windows не поддерживает следующие возможности CRT.  
  
-   Большая часть функций CRT, связанных с неподдерживаемой функциональностью.  
  
     Например, приложение [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] не может создать процесс с помощью семейств подпрограмм `exec` и `spawn`.  
  
     Если функция CRT не поддерживается в приложении [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], это указывается в статье по данной функции.  
  
-   Большая часть функций, работающих с многобайтовыми символами и строками.  
  
     Однако тексты Юникод и ANSI поддерживаются.  
  
-   Консольные приложения и аргументы командной строки.  
  
     Однако классические приложения по-прежнему поддерживают консоль и аргументы командной строки.  
  
-   Переменные среды.  
  
-   Понятие текущего рабочего каталога.  
  
-   Приложения и DLL [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], которые статически связаны с CRT и собираются с использованием параметров компилятора [/MT](../build/reference/md-mt-ld-use-run-time-library.md) или `/MTd`.  
  
     Это означает, что приложение использует многопоточную статическую версию CRT.  
  
-   Приложения, которые создаются с использованием параметра компилятора [/MDd](../build/reference/md-mt-ld-use-run-time-library.md).  
  
     То есть, отладочная, многопоточная и DLL-специфичная версия CRT. Такое приложение не поддерживается в [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)].  
  
 Полный список функций CRT, которые недоступны в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], и альтернативные предложения можно изучить в статье [CRT functions not supported with /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx). (Функции CRT, которые не поддерживаются при использовании ключа /ZW).  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)   
 [Функции CRT, которые не поддерживаются средой выполнения Windows](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)
