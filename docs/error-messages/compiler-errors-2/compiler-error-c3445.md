---
title: "C3445 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 04/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3445
dev_langs: C++
helpviewer_keywords: C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf0ba819aa1e8f0a7651e7c42e457b5766c9eefd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  