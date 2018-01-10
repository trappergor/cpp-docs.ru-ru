---
title: "(Уровень 3) предупреждение компилятора C4800 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4800
dev_langs: C++
helpviewer_keywords: C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 687b0dab996bfbfe2ce30d65b86196383c02b914
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4800"></a>Предупреждение компилятора (уровень 3) C4800  
  
> "*типа*": принудительно задано логическое значение «true» или «false» (предупреждение о производительности)  
  
Это предупреждение создается в том случае, если значение, не `bool` присваивается или преобразуется в тип `bool`. Как правило, это сообщение вызвано назначение `int` переменных `bool` переменных где `int` переменная содержит только значения **true** и **false**и может быть повторно объявлен как тип `bool`. Если невозможно перезаписать выражение для использования типа `bool`, затем можно добавить «`!=0`» к выражению, предоставляющего тип выражения `bool`. Приведение выражения к типу `bool` не отключайте предупреждение, что было сделано намеренно.  
  
Это предупреждение больше не создается в Visual Studio 2017 г.  
  
## <a name="example"></a>Пример
  
 Следующий пример приводит к возникновению ошибки C4800 и приводятся сведения по ее устранению.  
  
```cpp  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // To fix, instead try:  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```