---
title: "C3445 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3445
dev_langs:
- C++
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: c89d7f1f13829422a330960ac319531fc551fb97
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3445"></a>C3445 ошибки компилятора
Список инициализация копии из "*типа*" нельзя использовать явный конструктор  
  
В соответствии с ISO стандарт C ++ 17 компилятор должен учитывать явный конструктор для разрешения перегрузки в инициализация копии списка, но необходимо создание ошибки, если фактический Выбор этой перегрузки.  
  
Начиная с Visual Studio 2017 г., то компилятор находит ошибки, связанные с создания объекта с помощью списка инициализаторов, которые не были найдены по Visual Studio 2015. Эти ошибки может привести к сбоям или неопределенное поведение во время выполнения.

## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3445.  
  
```cpp  
// C3445.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of 
                      //     'A' cannot use an explicit constructor
}
```  
  
Чтобы исправить эту ошибку, используйте прямой инициализации.  
  
```cpp  
// C3445b.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1{ 1 };
}  
```  
  
