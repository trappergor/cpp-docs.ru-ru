---
title: "Ошибка средств компоновщика LNK1223 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1223"
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка средств компоновщика LNK1223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata  
  
 Для RISC\-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.  
  
 Чтобы устранить эту проблему, попробуйте компилировать без включенного параметра [\/GL \(Whole Program Optimization\)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md).  Также в некоторых случаях эта ошибка может возникнуть из\-за пустого текста функций.