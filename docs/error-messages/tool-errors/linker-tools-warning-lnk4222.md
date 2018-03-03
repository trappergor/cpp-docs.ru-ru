---
title: "Предупреждение средств компоновщика LNK4222 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a54c452a5df6f99260d6d01fbf4bb9f2f17b955
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4222"></a>Предупреждение средств компоновщика LNK4222
экспортированному символу «символ» не следует присваивать порядковое число  
  
 Следующие символы не должны быть экспортированы по порядковому номеру:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Эти функции всегда находятся по имени, с помощью `GetProcAddress`. Компоновщик предупреждает об этом типе экспорта, поскольку это может привести к более крупного изображения. Это может произойти, если диапазон порядковых номеров экспортов велик с относительно небольшим числом экспортов. Например, примененная к объекту директива  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 потребуется 100 областей в таблице экспорта адресов с 98 их просто заполнитель (2-99). С другой стороны  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 потребуется две области. (Имейте в виду, что можно также экспортировать [и экспорт](../../build/reference/export-exports-a-function.md) компоновщика.)