---
title: "Предупреждение (уровень 1) C4667 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4667
dev_langs: C++
helpviewer_keywords: C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fd488cc755bf805ec9af469cabab77108565f37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4667"></a>Предупреждение компилятора (уровень 1) C4667
«функция»: функция шаблон не определен, соответствующий принудительному созданию экземпляра  
  
 Не удается создать экземпляр шаблона функции, который не был объявлен.  
  
 Следующий пример вызывает ошибку C4667:  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 Чтобы избежать этого предупреждения, необходимо сначала объявите шаблон функции:  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```