---
title: "Ошибка средств компоновщика LNK1107 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1107
dev_langs: C++
helpviewer_keywords: LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fae412de31163aa1b5248af43227042cd04563ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1107"></a>Ошибка средств компоновщика LNK1107
Недопустимый или поврежденный файл: не удается прочитать в расположении  
  
 Средство не удалось прочитать файл. Повторно создайте файл.  
  
 LNK1107 также может возникать при попытке передачи модуля (расширение DLL или NETMODULE-файл, созданных с помощью [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) или [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) в компоновщик; передать OBJ-файле вместо.  
  
 При компиляции следующего примера:  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 затем укажите **связать LNK1107.dll** в командной строке, произойдет ошибка LNK1107.  Чтобы устранить эту ошибку, укажите **связать LNK1107.obj** вместо него.