---
title: "Запечатывание виртуальной функции | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__sealed - ключевое слово"
  - "производные классы, виртуальные функции"
  - "sealed - ключевое слово [C++]"
  - "виртуальные функции, запечатывание"
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Запечатывание виртуальной функции
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] синтаксис запечатывания виртуальной функции отличается от управляемых расширений для C\+\+.  
  
 В управляемых расширениях ключевое слово `__sealed` используется для изменения ссылочного типа, запрещая последующее наследование от него \(см. раздел [Объявление управляемых типов классов](../dotnet/declaration-of-a-managed-class-type.md)\), или для изменения виртуальной функции, запрещая последующее переопределение метода в производном классе.  Примеры.  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 В этом примере метод `derived::f()` переопределяет метод экземпляра `base::f()` на основании точного соответствия прототипа функции.  Ключевое слово `__sealed` определяет, что в классах, наследуемых от производного класса, не допускается переопределение метода `derived::f()`.  
  
 В новом синтаксисе ключевое слово `sealed` размещается после подписи, а не в любом месте до фактического прототипа функции, что было допустимо в старом синтаксисе.  Кроме того, при использовании ключевого слова `sealed` необходимо явно использовать ключевое слово `virtual`.  Учитывая это, правильное преобразование класса `derived` будет выглядеть следующим образом:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Отсутствие ключевого слова `virtual` в этом экземпляре приведет к ошибке.  Чтобы определить чисто виртуальную функцию в новом синтаксисе, следует использовать контекстно\-зависимое ключевое слово `abstract` вместо ключевого слова `=0`.  В управляемых расширениях такой синтаксис не поддерживается.  Примеры.  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 Приведенный выше код можно изменить следующим образом:  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [запечатанные](../windows/sealed-cpp-component-extensions.md)