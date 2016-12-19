---
title: "Выгрузка библиотеки DLL, загруженной с задержкой | Microsoft Docs"
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
  - "__FUnloadDelayLoadedDLL2"
  - "отложенная загрузка библиотек DLL, выгрузка"
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Выгрузка библиотеки DLL, загруженной с задержкой
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вспомогательная функция отложенной загрузки, предоставляемая по умолчанию, выполняет проверку на предмет наличия в поле pUnloadIAT указателей дескриптора отложенной загрузки, а также копии исходной адресной таблицы импорта \(IAT\).  Если результат проверки положительный, функция сохраняет указатель в списке дескрипторов отложенной загрузки.  Таким образом, вспомогательная функция включается для поиска по именам библиотек DLL, чтобы обеспечить поддержку явной выгрузки библиотек DLL.  
  
 Далее приведены связанные структуры и функции для явной выгрузки библиотеки DLL, загруженной с задержкой:  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 Структура UnloadInfo реализуется с помощью класса C\+\+, использующего реализации **LocalAlloc** и **LocalFree** в качестве операторов **создать** и **удалить** соответственно.  Данные параметры содержатся в стандартном связанном списке, в котором в качестве заголовка используется \_\_puiHead.  
  
 При вызове \_\_FUnloadDelayLoadedDLL будет выполнен поиск по имени, заданному в списке загруженных библиотек DLL \(по точному совпадению\).  Если результат поиска положительный, копия IAT а UnloadIAT записывается поверх работающей IAT, чтобы восстановить указатели преобразователя, библиотека высвобождается посредством **FreeLibrary**, связывание соответствующей записи **UnloadInfo** списка отменяется, запись удаляется, и возвращается значение true.  
  
 Для аргумента функции \_\_FUnloadDelayLoadedDLL2 регистр учитывается.  Например, можно указать:  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 но не:  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## См. также  
 [Understanding the Helper Function](http://msdn.microsoft.com/ru-ru/6279c12c-d908-4967-b0b3-cabfc3e91d3d)