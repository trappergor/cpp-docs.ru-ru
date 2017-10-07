---
title: "свойство (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d4cb68d02f9ee543c2d3271bc48ad4318352faa2
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="property-c"></a>property (C++)
**Блок, относящийся только к системам Майкрософт**  
  
 Этот атрибут может применяться к нестатическим "виртуальным данным-членам" в определении класса или структуры. Компилятор обрабатывает эти "виртуальные данные-члены" как данные-член, заменяя ссылки вызовами функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор обнаруживает данные-член с этим атрибутом в правой части оператора выбора члена (»**.**«или»**->**»), он преобразует операцию **получить** или **поместить** функции, в зависимости от того, является ли это выражение значением l-value или r-value. В более сложных контекстах, например «`+=`«, перезапись выполняется с использованием обеих **получить** и **поместить**.  
  
 Этот атрибут также может использоваться при объявлении пустого массива в определении класса или структуры. Например:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 Приведенный выше оператор указывает, что `x[]` может использоваться с одним или несколькими индексами массива. В этом случае выражение `i=p->x[a][b]` будет преобразовано в `i=p->GetX(a, b)`, а выражение `p->x[a][b] = i` будет преобразовано в `p->PutX(a, b, i);`  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [__declspec](../cpp/declspec.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)
