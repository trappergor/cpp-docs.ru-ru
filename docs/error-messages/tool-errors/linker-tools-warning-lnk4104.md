---
title: Предупреждение средств компоновщика LNK4104 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9ea3e074cc0db9591cd0ffe9329ff7f1936563f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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