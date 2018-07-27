---
title: Неустранимая ошибка C1197 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dacd459729161cf635287697a4a6d35c15eab3e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227284"
---
# <a name="fatal-error-c1197"></a>Неустранимая ошибка C1197
не может ссылаться «mscorlib.dll_1», так как программой был уже адресован «mscorlib.dll_2»  
  
 Компилятор соответствует версии среды CLR.  Однако попытка сослаться на версию файле среды CLR из предыдущей версии.  
  
 Чтобы устранить эту ошибку, только ссылки на файлы из версии общеязыковой среды выполнения, которая поставлялась с версией Visual C++ при компиляции с параметром.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C1197:  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```