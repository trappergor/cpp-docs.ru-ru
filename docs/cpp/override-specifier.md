---
title: "Спецификатор override | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "override - идентификатор"
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Спецификатор override
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `override` можно использовать для обозначения функций\-членов, переопределяющих виртуальную функцию в базовом классе.  
  
## Синтаксис  
  
```  
  
function-declaration override;  
```  
  
## Заметки  
 Ключевое слово `override` является контекстным и имеет специальное значение, только если используется после объявления функции\-члена; в противном случае оно не является зарезервированным ключевым словом.  
  
## Пример  
 С помощью `override` можно избежать случайного поведения наследования в коде.  В следующем примере показано, в какой ситуации без использования `override` поведение функции\-члена производного класса может быть случайным.  Компилятор не выдает ошибки при использовании этого кода.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
  
};  
  
```  
  
 При использовании `override` компилятор создает ошибки вместо того, чтобы автоматически создавать новые функции\-члены.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
  
```  
  
 Чтобы запретить переопределение функций и наследование классов, используйте ключевое слово [final](../cpp/final-specifier.md).  
  
## См. также  
 [Спецификатор final](../cpp/final-specifier.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/ru-ru/b53ba470-e583-4e5c-b634-6018f6110674)