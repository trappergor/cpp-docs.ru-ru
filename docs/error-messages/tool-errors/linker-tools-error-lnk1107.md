---
title: Ошибка средств компоновщика LNK1107 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fee2105cb0c12287cd2b47636f0e47011854a608
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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