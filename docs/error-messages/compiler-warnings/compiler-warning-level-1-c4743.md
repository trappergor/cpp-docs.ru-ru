---
title: Предупреждение (уровень 1) C4743 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4743
dev_langs:
- C++
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84b4d5f3aa465257d7efcf9f95584612214165b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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