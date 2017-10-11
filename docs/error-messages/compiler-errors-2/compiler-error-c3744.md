---
title: "Ошибка компилятора C3744 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 87df3fd92ac3fcad9b3e87f02f16b8151e678b77
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744
для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий  
  
 [__Unhook](../../cpp/unhook.md) функция должна принимать три параметра в программе, которая компилируется для управляемых расширений для C++.  
  
 `__hook`и `__unhook` не совместимы с параметром/CLR. Вместо этого используйте операторов += и-=.  
  
 C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  

