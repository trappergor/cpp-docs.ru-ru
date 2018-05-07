---
title: Выгрузка библиотеки DLL, загружаемых с задержкой | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724ee2ac3987c855f5e2102dee35d12785726641
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="unloading-a-delay-loaded-dll"></a>Выгрузка библиотеки DLL, загруженной с задержкой
Вспомогательный объект отложенной загрузки, предоставляемая по умолчанию проверяет дескрипторы отложенной загрузки наличие указателя и копия исходной таблицы адресов импорта (IAT) в поле pUnloadIAT. В этом случае указатель будет сохранен в список для импорта дескриптора задержки. Это позволяет вспомогательную функцию для поиска библиотеки DLL по имени, для поддержки явно выгрузки библиотек DLL.  
  
 Ниже приведены связанные структуры и функции для явная выгрузка библиотеки DLL, загружаемых с задержкой.  
  
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
  
 Структура UnloadInfo реализуется с помощью класса C++, который использует **LocalAlloc** и **LocalFree** реализации как своего оператора **новый** и оператор  **Удалить** соответственно. Эти параметры хранятся в стандартных связанного списка, используя __puiHead как начало списка.  
  
 Вызов __FUnloadDelayLoadedDLL будет найти имя указываются в списке загруженных библиотек DLL (точное соответствие не требуется). Если найден, копия IAT а UnloadIAT копируется поверх работающей IAT, чтобы восстановить указатели преобразователя, библиотека высвобождается с **FreeLibrary**, соответствующего **UnloadInfo** запись не будет связан с список и удаляются и возвращается значение TRUE.  
  
 Аргумент для функции __FUnloadDelayLoadedDLL2 учитывается регистр символов. Например необходимо указать:  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 а не:  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## <a name="see-also"></a>См. также  
 [Понятие вспомогательной функции](understanding-the-helper-function.md)