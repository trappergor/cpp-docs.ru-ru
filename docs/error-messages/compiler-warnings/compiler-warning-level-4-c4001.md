---
title: Предупреждение (уровень 4) компилятора C4001 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4001
dev_langs:
- C++
helpviewer_keywords:
- C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc728fa5c66fb4b42c8fe4a785f36048ffbaed4e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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