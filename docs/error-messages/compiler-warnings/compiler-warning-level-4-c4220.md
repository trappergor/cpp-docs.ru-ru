---
title: "Предупреждение (уровень 4) C4220 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4220
dev_langs: C++
helpviewer_keywords: C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdcaeb5ec7e3b7258b9bb7b3edc188038e648c99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4220"></a>Предупреждение компилятора (уровень 4) C4220
varargs соответствует оставшимся параметрам  
  
 При использовании расширений Майкрософт по умолчанию (/Ze) указатель на функцию соответствует указатель на функцию с аналогичными, но переменными, аргументы.  
  
## <a name="example"></a>Пример  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Такие указатели не совпадают в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).