---
title: "Ошибка средств компоновщика LNK1302 | Microsoft Docs"
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
  - "LNK1302"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1302"
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1302
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

поддерживаются только ссылки безопасное .netmodules; не удается выполнить компоновку .netmodule  
  
 \(.netmodule Компилированное с **\/LN**\) было передано компоновщиком при попытке пользователя вызвать связывание MSIL.  Компоновка MSIL модуля C\+\+ допустима, только если он скомпилирован с параметром **\/clr:safe**.  
  
 Чтобы устранить данную ошибку, произведите компиляцию с параметром **\/clr:safe**, чтобы сделать возможной компоновку MSIL, либо передайте компоновщику вместо модуля OBJ\-файл **\/clr** или **\/clr:pure**.  
  
 Дополнительные сведения см. в следующем разделе.  
  
-   [\/LN \(создание модуля MSIL\)](../../build/reference/ln-create-msil-module.md)  
  
-   [.NETMODULE\-файлы в качестве входных файлов компоновщика](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)