---
title: "Предупреждение средств компоновщика LNK4224 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96399e0c66eb3cb719073b2318513cd680723d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4224"></a>Предупреждение средств компоновщика LNK4224
параметр больше не поддерживается; обрабатывается  
  
 Недопустимый устаревший параметр компоновщика был указан и игнорируются.  
  
 Например, LNK4224 может возникать, если директива/Comment отображается в. obj. Директива/Comment добавляемого через [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md) pragma, с помощью параметром exestr. Использование служебной программы dumpbin [/ALL](../../build/reference/all.md) Просмотр директивы компоновщика в OBJ-файле.  
  
 Если это возможно изменить источник для OBJ-файл и удалите директиву pragma. Если пропустить это предупреждение, это может означать, что ошибок компиляции с **/CLR: pure** не будет работать ожидаемым образом.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки LNK4224.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```