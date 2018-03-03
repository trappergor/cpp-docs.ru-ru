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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd5c11e88960f2b4332a586d2fe982a8ea94fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744
для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий  
  
 [__Unhook](../../cpp/unhook.md) функция должна принимать три параметра в программе, которая компилируется для управляемых расширений для C++.  
  
 `__hook`и `__unhook` не совместимы с параметром/CLR. Вместо этого используйте операторов += и-=.  
  
 C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  
