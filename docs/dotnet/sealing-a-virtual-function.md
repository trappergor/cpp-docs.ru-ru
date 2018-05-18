---
title: Запечатывание виртуальной функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c85f4775025d3661fdfbf8967b310fb733f452b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sealing-a-virtual-function"></a>Запечатывание виртуальной функции
Синтаксис Запечатывание виртуальной функции отличается от управляемых расширений для C++ к Visual C++.  
  
 `__sealed` Ключевое слово используется в управляемых расширениях для изменения любого ссылочного типа, запрещая последующее наследование от него (в разделе [объявления типа управляемого класса](../dotnet/declaration-of-a-managed-class-type.md)), или изменить виртуальную функцию, запрет последующее переопределение метода в производном классе. Пример:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 В этом примере `derived::f()` переопределяет `base::f()` по совпадению прототип функции. `__sealed` Ключевое слово указывает, что классах, наследуемых от производного класса не допускается переопределение `derived::f()`.  
  
 В новом синтаксисе `sealed` размещается после подписи, а не находиться в любом месте до фактического прототипа функции, что было допустимо. Кроме того, использование `sealed` необходимо использовать явную `virtual` также ключевое слово. То есть правильное преобразование `derived`выше, выглядит следующим образом:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Отсутствие `virtual` ключевое слово в данном экземпляре приводит к ошибке. В новом синтаксисе контекстно-зависимое ключевое слово `abstract` может использоваться вместо `=0` для указания чистой виртуальной функции. Это не поддерживается в управляемых расширениях. Пример:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 можно переписать следующим образом  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)