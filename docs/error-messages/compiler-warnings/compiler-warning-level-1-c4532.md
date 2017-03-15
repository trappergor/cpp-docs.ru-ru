---
title: "Предупреждение компилятора (уровень 1) C4532 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4532"
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 1) C4532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"продолжить": для перехода из блока \_\_finally\/finally не определено поведение при обработке завершения  
  
 Компилятор обнаружил одно из следующих ключевых слов:  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 что вызвало переход из блока [\_\_finally](../../cpp/try-finally-statement.md) или [finally](../../dotnet/finally.md) во время аварийного завершения.  
  
 При возникновении исключения, когда стек развертывается во время выполнения обработчиков завершения \(блоков `__finally` или блоков finally\), и код переходит из блока `__finally` до завершения блока `__finally`, поведение не задано.  Элемент управления не может быть возвращен в развертываемый код, поэтому исключение не может быть обработано должным образом.  
  
 Если необходим переход из блока **\_\_finally**, следует вначале выполнить проверку на предмет аварийного завершения.  
  
 Следующий пример также демонстрирует причины возникновения ошибки C4532; чтобы разрешить предупреждения, следует просто преобразовать операторы в комментарии.  
  
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