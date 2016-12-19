---
title: "Предупреждение средств компоновщика LNK4086 | Microsoft Docs"
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
  - "LNK4086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4086"
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

точка входа функции 'function' не равна \_\_stdcall с количеством 'number' байт аргументов; образ может не запускаться  
  
 точка входа для библиотеки DLL должна быть `__stdcall`.  Повторите компиляцию функцию с параметром [\/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) или укажите `__stdcall` или WINAPI при определении функции.