---
title: "Явная выгрузка библиотеки DLL, загруженной с задержкой | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY:UNLOAD - параметр компоновщика"
  - "__FUnloadDelayLoadedDLL2"
  - "DELAY:UNLOAD - параметр компоновщика"
  - "отложенная загрузка библиотек DLL, выгрузка"
ms.assetid: 1c4c5172-fd06-45d3-9e4f-f12343176b3c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Явная выгрузка библиотеки DLL, загруженной с задержкой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметр компоновщика [\/delay](../../build/reference/delay-delay-load-import-settings.md):unload позволяет выгружать библиотек DLL, загруженную с задержкой.  По умолчанию, когда код выгружает библиотеку DLL \(используя \/delay:unload и **\_\_FUnloadDelayLoadedDLL2**\), импортирование, загружаемое с задержкой, остается в таблице импорта адресов \(IAT\).  Тем не менее, при использовании в командной строке построителя \/delay:unload, функция помощника будет поддерживать явную выгрузку библиотеки DLL, сбрасывая значения IAT в первоначальное состояние. Недействительные в данный момент указатели будут перезаписаны.  IAT является полем [ImgDelayDescr](../../build/reference/calling-conventions-parameters-and-return-type.md), содержащим адрес копии оригинальной IAT \(если она существует\).  
  
## Пример  
  
### Код  
  
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
  
### Комментарии  
 Важные замечания при выгрузке библиотеки DLL, загруженной с задержкой:  
  
-   Описание процесса реализации функции **\_\_FUnloadDelayLoadedDLL2** можно найти в файле \\VC7\\INCLUDE\\DELAYHLP.CPP.  
  
-   Имя параметра функции **\_\_FUnloadDelayLoadedDLL2** должно полностью совпадать \(включая регистр\) с содержимым библиотеки импорта \(эта строка тоже находится в таблице импорта образа\).  Содержимое библиотеки импорта можно посмотреть с использованием параметра [DUMPBIN \/DEPENDENTS](../Topic/-DEPENDENTS.md).  В нечувствительных к регистру строках совпадение не обязательно, **\_\_FUnloadDelayLoadedDLL2** можно обновить для использования функций CRT\-строки или вызова Windows API.  
  
 Дополнительные сведения см. в разделе [Выгрузка библиотеки DLL, загруженной с задержкой](../../build/reference/unloading-a-delay-loaded-dll.md).  
  
## См. также  
 [Поддержка компоновщика для DLLs, загружаемых с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)