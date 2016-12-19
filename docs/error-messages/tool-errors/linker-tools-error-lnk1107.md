---
title: "Ошибка средств компоновщика LNK1107 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый или поврежденный файл: не удается прочитать по location  
  
 Инструменту не удалось прочитать файл.  Создайте файл повторно.  
  
 Ошибка LNK1107 также может возникать при попытке загрузить модуль \(DLL или расширение .netmodule созданные с помощью [\/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) или [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)\) компоновщику; передайте OBJ\-файл вместо.  
  
 При компиляции следующего примера:  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 и последующем указании в командной строке команды **link LNK1107.dll** произойдет ошибка LNK1107.  Для устранения этой ошибки используйте вместо этого команду **link LNK1107.obj**.