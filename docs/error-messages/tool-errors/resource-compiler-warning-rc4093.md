---
title: "Предупреждение компилятора ресурсов RC4093 | Microsoft Docs"
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
  - "RC4093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4093"
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора ресурсов RC4093
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

знак новой строки без escape\-последовательности в символьной константе в неактивном коде  
  
 Вычислено нулевое значение выражения константы директивы препроцессора `#if`, `#elif`, **\#ifdef** или **\#ifndef**, что делает следующий код неактивным.   Внутри этого неактивного кода знак новой строки заключен в одинарные или двойные кавычки.  
  
 Весь текст до следующих двойных кавычек рассматривается как заключенный внутри символьной константы.