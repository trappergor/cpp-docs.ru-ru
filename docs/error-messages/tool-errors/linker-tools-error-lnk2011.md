---
title: Ошибка средств компоновщика LNK2011 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f60dce4cb260c670f5ee82aa88b9f106f3f14e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2011"></a>Ошибка средств компоновщика LNK2011
предварительно скомпилированный объект, не связаны; образ нельзя запустить  
  
 При использовании предкомпилированных заголовков LINK необходимо, чтобы все объектные файлы, созданные с предкомпилированными заголовками, быть скомпонованы. Если у вас есть исходный файл, который можно использовать для создания предкомпилированного заголовка для использования в других исходных файлов, теперь необходимо включить объектный файл, созданный вместе с предкомпилированного заголовка.  
  
 Например если скомпилировать файл с именем STUB.cpp для создания предкомпилированного заголовка для использования с другими исходными файлами, необходимо связать с STUB.obj или эта ошибка возникает. В следующих командных строк строка используется для создания предкомпилированного заголовка COMMON.pch, который используется с PROG1.cpp и PROG2.cpp в строках, 2 и 3. Файл STUB.cpp содержит только `#include` строк (же `#include` строк как PROG1.cpp и PROG2.cpp) и используется только для создания предкомпилированных заголовков. В последней строке STUB.obj должны быть связаны в во избежание LNK2011.  
  
```  
cl /c /Yccommon.h stub.cpp  
cl /c /Yucommon.h prog1.cpp  
cl /c /Yucommon.h prog2.cpp  
link /out:prog.exe stub.obj prog1.obj prog2.obj  
```