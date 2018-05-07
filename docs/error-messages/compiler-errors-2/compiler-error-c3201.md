---
title: Ошибка компилятора C3201 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51ebf253a1d1e5963ff05aa343295e133a0641c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3201"></a>Ошибка компилятора C3201
список параметров шаблона для класса-шаблона template не совпадает со списком параметров шаблона для параметра шаблона template  
  
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