---
title: "Предупреждение (уровень 2) C4244 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4244
dev_langs: C++
helpviewer_keywords: C4244
ms.assetid: 2c19d157-21d1-42c2-a6c0-3f30f2ce3813
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7f2059d6b17d803740f70e0d640e212d15858705
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4244"></a>Предупреждение компилятора (уровень 2) C4244
«аргумент»: преобразование из «тип1» в «тип2», возможна потеря данных  
  
 Значение с плавающей запятой был преобразован в тип integer.  Возможна потеря данных.  
  
 При возникновении ошибки C4244 следует изменить программу так, чтобы использовались совместимые типы, или добавить в код логику, чтобы диапазон возможных значений всегда был совместим с типами, которые вы используете.  
  
 Предупреждение C4244 также может возникнуть на уровне 3 и 4. в разделе [Предупреждение компилятора (уровни 3 и 4) C4244](../../error-messages/compiler-warnings/compiler-warning-levels-3-and-4-c4244.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4244.  
  
```  
// C4244_level2.cpp  
// compile with: /W2  
  
int f(int x){ return 0; }  
int main() {  
   double x = 10.1;  
   int i = 10;  
   return (f(x));   // C4244  
   // try the following line instead  
   // return (f(i));  
}  
```