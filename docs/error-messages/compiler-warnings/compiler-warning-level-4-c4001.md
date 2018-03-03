---
title: "Предупреждение (уровень 4) компилятора C4001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b5c3d82bef81ee84514b39a0ce8ab07ad6e6c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4001"></a>Компилятора C4001 предупреждение (уровень 4)
было использовано нестандартное расширение «однострочного комментария»  

> [!NOTE] 
> Это предупреждение удаляется в версии 15,5 2017 г. Visual Studio, так как однострочные комментарии являются стандартными в C99.
  
 Однострочные комментарии являются стандартными в C++ и стандартная в C, начиная с C99. В строгом режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), файлы C, содержащие однострочные комментарии, создают ошибку C4001 из-за использования нестандартного расширения. Поскольку однострочных комментариев являются стандартными в C++, файлы C, содержащие однострочные комментарии не создают C4001 при компиляции с расширениями Майкрософт (/Ze).  
  
## <a name="example"></a>Пример  
 Чтобы отключить предупреждение, раскомментируйте [#pragma warning(disable:4001)](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```