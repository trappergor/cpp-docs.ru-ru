---
title: "Ошибка компилятора C3744 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: f6cd256454b51a103d9c4249b050c8c05781bc78
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3744"></a>Ошибка компилятора C3744
для __unhook требуется по крайней мере 3 аргумента в случае управляемых событий  
  
 [__Unhook](../../cpp/unhook.md) функция должна принимать три параметра в программе, скомпилированной для управляемых расширений для C++.  
  
 `__hook`и `__unhook` не совместимы с параметром/CLR. Вместо этого используются операторы += и-=.  
  
 C3744 доступен только с помощью параметра компилятора устаревшие **/CLR: oldSyntax**.  

