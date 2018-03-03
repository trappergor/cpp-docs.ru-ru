---
title: "Ошибка компилятора предупреждение (уровень 4) C4629 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4629
dev_langs:
- C++
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2d07d2d105c82d1175a9c7cde0326732f0677f35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4629"></a>Предупреждение компилятора (уровень 4) C4629
использован диграф, последовательность знаков digraph интерпретирована как токен char (если требуется другой результат, добавьте пробел между двумя знаками)  
  
 При использовании параметра [/Za](../../build/reference/za-ze-disable-language-extensions.md)компилятор выдает предупреждение, когда обнаруживает диграф.  
  
 В следующем примере возникает ошибка C4629.  
  
```  
// C4629.cpp  
// compile with: /Za /W4  
int main()  
<%   // C4629 <% digraph for {  
}  
```