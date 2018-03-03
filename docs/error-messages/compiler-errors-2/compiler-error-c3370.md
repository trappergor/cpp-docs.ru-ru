---
title: "Ошибка компилятора C3370 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3370
dev_langs:
- C++
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 01ca951f6acd8af2fbbdba3d84b82a441cd7e92b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3370"></a>Ошибка компилятора C3370
"имя_модуля_idl": idl_module еще не определен  
  
 Прежде чем использовать [idl_module](../../windows/idl-module.md) для указания точки входа в DLL, вы должны сначала с помощью `idl_module` указать имя библиотеки DLL.  
  
 В следующем примере возникает ошибка C3370:  
  
```  
// C3370.cpp  
[module(name=MyLibrary)];  
// uncomment the following line to resolve the error  
// [idl_module(name="name1", dllname=x.dll)];  
[idl_module(name="name1"), entry(100)] // C3370  
int f1();  
  
int main()  
{  
}  
```