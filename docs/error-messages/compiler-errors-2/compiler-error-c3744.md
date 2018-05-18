---
title: Ошибка компилятора C3744 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f96b8445c343bdd4f606157e692c4d6ce262e369
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744
для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий  
  
 [__Unhook](../../cpp/unhook.md) функция должна принимать три параметра в программе, которая компилируется для управляемых расширений для C++.  
  
 `__hook` и `__unhook` не совместимы с параметром/CLR. Вместо этого используйте операторов += и-=.  
  
 C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  
