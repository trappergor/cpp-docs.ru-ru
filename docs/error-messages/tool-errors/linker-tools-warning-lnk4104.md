---
title: "Предупреждение средств компоновщика LNK4104 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4104
dev_langs: C++
helpviewer_keywords: LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d049ef8663798236250977e90d12c2971dec443
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4104"></a>Предупреждение средств компоновщика LNK4104
Экспорт символа «символ» должен быть PRIVATE  
  
 `symbol` Может принимать одно из следующих действий:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 Это предупреждение создается при создании библиотеки импорта для библиотеки DLL и экспортировать один из перечисленных выше функций без указания ее как PRIVATE в файле определения модуля. В общем случае эти функции экспортируются для использования только в OLE. Поместив их в библиотеку импорта может привести к непредвиденному поведению, когда программа связана с библиотекой неправильно выполняет вызовы к ним. Дополнительные сведения о ключевом слове PRIVATE см. в разделе [ЭКСПОРТОВ](../../build/reference/exports.md).