---
title: "property (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "property_cpp"
  - "Property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], свойство"
  - "property __declspec - ключевое слово"
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# property (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Этот атрибут может применяться к нестатическим "виртуальным данным\-членам" в определении класса или структуры.  Компилятор обрабатывает эти "виртуальные данные\-члены" как данные\-член, заменяя ссылки вызовами функций.  
  
## Синтаксис  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## Заметки  
 Когда компилятор обнаруживает данные\-член с этим атрибутом в правой части оператора выбора члена \("**.**" или "**\-\>**"\), он преобразует операцию в функцию **get** или **put**, в зависимости от того, является ли это выражение значением l\-value или r\-value.  В более сложных контекстах, например "`+=`", перезапись выполняется с использованием обеих функций **get** и **put**.  
  
 Этот атрибут также может использоваться при объявлении пустого массива в определении класса или структуры.  Например:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 Приведенный выше оператор указывает, что `x[]` может использоваться с одним или несколькими индексами массива.  В этом случае выражение `i=p->x[a][b]` будет преобразовано в `i=p->GetX(a, b)`, а выражение `p->x[a][b] = i` будет преобразовано в `p->PutX(a, b, i);`  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## Пример  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)