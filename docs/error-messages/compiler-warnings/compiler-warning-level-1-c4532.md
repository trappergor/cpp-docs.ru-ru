---
title: "Предупреждение (уровень 1) C4532 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4532
dev_langs:
- C++
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44aae61190b20bf1ef93b586c02e88837d487324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4532"></a>Предупреждение компилятора (уровень 1) C4532
«continue»: переход из блока __finally/finally не определено поведение при обработке завершения  
  
 Компилятор обнаружил одно из следующих ключевых слов:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 что вызвало переход из [__finally](../../cpp/try-finally-statement.md) или [наконец](../../dotnet/finally.md) блок во время аварийного завершения.  
  
 При возникновении исключения, и во время стек развертывается во время выполнения обработчиков завершения ( `__finally` или блоков finally), и код переходит из `__finally` блокировать перед `__finally` завершения блока, поведение не определено. Элемент управления могут не возвращать в развертываемый код, исключение не может быть обработано должным образом.  
  
 Если необходимо перейти из **__finally** блока, сначала проверьте аварийного завершения.  
  
 Следующий пример приводит к возникновению ошибки C4532; просто комментарий преобразовать операторы для разрешения предупреждения.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```