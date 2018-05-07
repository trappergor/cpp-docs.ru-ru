---
title: Предупреждение средств компоновщика LNK4224 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4224
dev_langs:
- C++
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a051e341a22871b4229617b3958cb68dedc2921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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