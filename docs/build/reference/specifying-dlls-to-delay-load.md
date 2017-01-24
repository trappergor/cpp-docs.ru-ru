---
title: "Задание библиотек DLL с отложенной загрузкой | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYLOAD - параметр компоновщика"
  - "отложенная загрузка библиотек DLL"
  - "отложенная загрузка библиотек DLL, определение"
  - "DELAYLOAD - параметр компоновщика"
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Задание библиотек DLL с отложенной загрузкой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вы можете указать, для каких библиотек DLL следует задержать загрузку с помощью параметра компоновщика [\/delayload](../../build/reference/delayload-delay-load-import.md):`dllname`.  Если вы не планируете использовать собственную версию вспомогательной функции, необходимо также связать программу с библиотекой delayimp.lib \(для классических приложений\) или dloadhelper.lib \(для приложений Магазина\).  
  
 Ниже приведен простой пример задержки загрузки библиотеки DLL.  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 Создание ОТЛАДОЧНОЙ версии проекта.  Просмотрите код, используя отладчик, и обратите внимание, что файл user32.dll загружается только при вызове `MessageBox`.  
  
## См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)