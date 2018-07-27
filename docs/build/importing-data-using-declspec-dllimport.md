---
title: Импорт данных с помощью __declspec(dllimport) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- importing data [C++]
- dllimport attribute [C++], data imports
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: 0ae70b39-87c7-4181-8be9-e786e0db60b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9877c5a229c3cabcb7703dd2617d1d57e3512f0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368516"
---
# <a name="importing-data-using-declspecdllimport"></a>Импорт данных с помощью объявления __declspec(dllimport)
В случае с данными, с помощью **__declspec(dllimport)** при работе, удаляет уровень косвенного обращения. При импорте данных из библиотеки DLL, все равно необходимо пройти через адресную таблицу импорта. Прежде чем **__declspec(dllimport)**, это означает, что необходимо сделать дополнительный уровень косвенного обращения при доступе к данным, экспортированным из библиотеки DLL:  
  
```  
// project.h  
#ifdef _DLL   // If accessing the data from inside the DLL  
   ULONG ulDataInDll;  
  
#else         // If accessing the data from outside the DLL  
   ULONG *ulDataInDll;  
#endif  
```  
  
 Необходимо выполнить экспорт данных в вашей. DEF-файл:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   CONSTANT  
```  
  
 и к нему доступ вне библиотеки DLL:  
  
```  
if (*ulDataInDll == 0L)   
{  
   // Do stuff here  
}  
```  
  
 Если пометить данные как **__declspec(dllimport)**, компилятор автоматически создает код косвенного обращения для вас. Больше не нужно беспокоиться о описанные выше действия. Как уже говорилось ранее, не следует использовать **__declspec(dllimport)** объявления данных при построении библиотеки DLL. Функций библиотеки DLL не используйте адресную таблицу импорта для доступа к объекту данных; Таким образом не будет иметь дополнительный уровень косвенного обращения.  
  
 Для автоматического экспорта данных из библиотеки DLL, используйте следующее объявление:  
  
```  
__declspec(dllexport) ULONG ulDataInDLL;  
```  
  
## <a name="see-also"></a>См. также  
 [Импорт в приложение](../build/importing-into-an-application.md)