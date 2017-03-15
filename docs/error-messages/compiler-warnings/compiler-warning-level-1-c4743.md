---
title: "Предупреждение компилятора (уровень 1) C4743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4743"
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Предупреждение компилятора (уровень 1) C4743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'*type*' имеет различные размеры в '*file1*' и '*file2*': *number* и *number* байт  
  
 Внешняя переменная, на которую указывает ссылка или которая определена в файлах 2 имеет различные типы в них, файлов, и компилятор определил, что размер переменной в *file1* отличается от размера переменной в *file2*.  
  
 Важно иметь в виду один случай, когда это предупреждение может выводиться для C\+\+.  Если в двух разных файлах объявлены одинаковые типы с одинаковыми именами, при том, что эти объявления неодинаковы и содержат виртуальные функции, компилятор может вывести предупреждение C4744 для таблиц виртуальных функций.  Причиной возникновения предупреждения является наличие двух таблиц виртуальных функций разного размера для одного и того же типа, и компоновщику приходится выбирать одну из них для включения в исполняемый файл.  Это может привести к тому, что программа вызовет неверную виртуальную функцию.  
  
 Чтобы устранить данную проблему, необходимо либо использовать одинаковое определение типа, либо задать разные имена для типов или переменных.  
  
## Пример  
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
  
## Пример  
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