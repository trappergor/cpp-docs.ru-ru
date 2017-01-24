---
title: "Ошибка компилятора C3201 | Microsoft Docs"
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
  - "C3201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3201"
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

список параметров шаблона для класса\-шаблона template не совпадает со списком параметров шаблона для параметра шаблона template  
  
 Вы передали шаблон класса в аргументе шаблону класса, не принимающему параметр шаблона, или вы передали несоответствующее число аргументов шаблона для аргумента шаблона по умолчанию.  
  
```  
// C3201.cpp  
template<typename T1, typename T2>  
class X1  
{  
};  
  
template<template<typename T> class U = X1>   // C3201  
class X2  
{  
};  
  
template<template<typename T, typename V> class U = X1>   // OK  
class X3  
{  
};  
```