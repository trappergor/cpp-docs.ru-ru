---
title: "Явная выгрузка библиотеки DLL, загружаемых с задержкой | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /DELAY:UNLOAD linker option
- DELAY:UNLOAD linker option
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b26a1a17952693be9db6a80649aad2c40227d53e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="explicitly-unloading-a-delay-loaded-dll"></a>Явная выгрузка библиотеки DLL, загруженной с задержкой
[/Delay](../../build/reference/delay-delay-load-import-settings.md): unload-параметр компоновщика позволяет выгружать библиотеку DLL, которая построена с отложенной загрузки. По умолчанию, когда ваш код выгружает библиотеку DLL (с помощью/DELAY: unload и **__FUnloadDelayLoadedDLL2**), импорты, загружаемые с задержкой, остаются в таблице адресов импорта (IAT). Однако при использовании/DELAY: unload в командной строке компоновщика вспомогательная функция будет поддерживать явную выгрузку библиотеки DLL, сбрасывая значения IAT в первоначальное состояние. Теперь недопустимые указатели будут перезаписаны. IAT является полем [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md) , содержащий адрес копии оригинальной IAT (если он существует).  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// link with /link /DELAYLOAD:MyDLL.dll /DELAY:UNLOAD  
#include <windows.h>  
#include <delayimp.h>  
#include "MyDll.h"  
#include <stdio.h>  
  
#pragma comment(lib, "delayimp")  
#pragma comment(lib, "MyDll")  
int main()  
{  
    BOOL TestReturn;  
    // MyDLL.DLL will load at this point  
    fnMyDll();  
  
    //MyDLL.dll will unload at this point  
    TestReturn = __FUnloadDelayLoadedDLL2("MyDll.dll");  
  
    if (TestReturn)  
        printf_s("\nDLL was unloaded");  
    else  
        printf_s("\nDLL was not unloaded");  
}  
```  
  
### <a name="comments"></a>Комментарии  
 Важные примечания по выгрузка библиотеки DLL, загружаемых с задержкой.  
  
-   Может найти реализацию **__FUnloadDelayLoadedDLL2** функции в файле \VC7\INCLUDE\DELAYHLP. CPP.  
  
-   Имя параметра **__FUnloadDelayLoadedDLL2** функции должно точно соответствовать (включая регистр) Библиотека импорта содержимое (которая также присутствует строка в таблице импорта на рисунке). Можно просмотреть содержимое библиотеки импорта с [DUMPBIN/DEPENDENTS](../../build/reference/dependents.md). Можно изменить, если требуется соответствие строк без учета регистра, **__FUnloadDelayLoadedDLL2** с использованием одного из строковых функций CRT, или вызов Windows API.  
  
 В разделе [выгрузка библиотеки DLL с Delay-Loaded](../../build/reference/unloading-a-delay-loaded-dll.md) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)