---
title: Предупреждение (уровень 4) C4289 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f7f09bd85d3740d43b6e4b6a80ed562f8cc2261
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4289"></a>Предупреждение компилятора (уровень 1) C4289
использовано нестандартное расширение : "переменная" : переменная управления циклом, объявленная в цикле for, используется вне области видимости этого цикла  
  
 При компиляции с параметром [/Ze](../../build/reference/za-ze-disable-language-extensions.md) и **/Zc: forScope**, переменной, объявленной в [для](../../cpp/for-statement-cpp.md) цикла использовался после **для**-области видимости цикла.  
  
 В разделе [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) сведения о способах указания стандартного поведения в **для** циклы **/Ze**.  
  
 Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .  
  
 Следующий пример приводит к возникновению ошибки C4289:  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```