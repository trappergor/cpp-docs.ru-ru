---
title: Загрузка всех импортов для библиотеки DLL, загружаемых с задержкой | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f054479a6681ba6de57690295fe3ce9f6c83696
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374376"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Загрузка всех импортов для библиотеки DLL с отложенной загрузкой
**__HrLoadAllImportsForDll** функции, которая определена в delayhlp.cpp, компоновщик должен загружать все импорты из библиотеки DLL, который был указан с [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) компоновщика.  
  
 Загрузка всех импортов позволяет поместить обработка ошибок в одном месте в коде и не должны использовать обработку исключений вокруг фактических вызовов импортов. Она также позволяет избежать ситуации, когда приложение не частично в процессе, в результате вспомогательной функции, не удается выполнить загрузку импорта.  
  
 Вызов **__HrLoadAllImportsForDll** не изменяет поведение обработчики и ошибок обработки; в разделе [обработка ошибок и уведомления](../../build/reference/error-handling-and-notification.md) для получения дополнительной информации.  
  
 Имя библиотеки DLL, передаваемый **__HrLoadAllImportsForDll** сравнивается с именем, хранящийся в самой библиотеки DLL и чувствительно к регистру.  
  
 В следующем примере демонстрируется вызов **__HrLoadAllImportsForDll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)