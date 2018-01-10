---
title: "Предупреждение (уровень 1) C4743 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4743
dev_langs: C++
helpviewer_keywords: C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a7169afdf7fb4c9a03e509f0332e738a66a06f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4743"></a>Предупреждение компилятора (уровень 1) C4743
"*тип*«имеет различные размеры»*file1*«и»*file2*": *номер* и *номер* байт  
  
 Внешняя переменная определена в двух файлах или ссылки на различные типы в эти файлы, а компилятор определила, что размер переменной в *file1* отличается от размера переменной в *file2*.  
  
 Это предупреждение может выводиться для C++ нет важный случай. Если объявить те же типы с тем же именем в разных файлах, если эти объявления содержат виртуальные функции, а объявления не совпадают, компилятор может вывести предупреждение C4744 для таблиц виртуальных функций. Предупреждение означает, что имеются две таблицы виртуальных функций разного размера для одного типа, и компоновщик необходимо выбрать один из них для включения в исполняемый файл.  Это возможно, что это может привести к программе, вызов неверную виртуальную функцию.  
  
 Чтобы устранить это предупреждение, используйте то же определение типа или используйте разные имена для типов или переменных.  
  
## <a name="example"></a>Пример  
 Этот пример содержит одно определение типа.  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4743.  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```