---
title: "Предупреждение средств компоновщика LNK4222 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4222
dev_langs:
- C++
helpviewer_keywords:
- LNK4222
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 8
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0948dc9de4d6b2c83e408b563e437f16b68f2fa4
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4222"></a>Предупреждение средств компоновщика LNK4222
экспортируемый символ «символ» не должен назначаться порядковому номеру  
  
 Следующие символы не должны быть экспортированы по порядковому номеру:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Эти функции всегда могут быть найдены по имени с помощью `GetProcAddress`. Компоновщик предупреждает об этом типе экспорта, поскольку это может привести к увеличенного изображения. Это может произойти, если диапазон порядковых номеров экспортов больше сравнительно небольшого количества экспортов. Например:  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 потребуется 100 областей в таблице экспорта адрес с 98 их просто заполнитель (2-99). С другой стороны  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 потребуется две области. (Имейте в виду, что можно также экспортировать [и экспорта](../../build/reference/export-exports-a-function.md) компоновщика.)
