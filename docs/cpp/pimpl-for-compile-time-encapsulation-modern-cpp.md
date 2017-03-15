---
title: "Pimpl для инкапсуляции времени компиляции (современный C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pimpl для инкапсуляции времени компиляции (современный C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*эта pimpl* современный метод C\+\+, чтобы скрывать реализацией, свернуть соединение и разделять интерфейсы.  Pimpl коротким «для указателя на реализацию». Можно быть уже знакомы с понятием только знать его различными именами, является брандмауэра котов или Чешира компилятора.  
  
## Зачем использовать pimpl?  
 Описание является pimpl может повысить жизненного цикла разработки программного обеспечения.  
  
-   Минимизация зависимостей компиляции.  
  
-   Разделение и реализации интерфейса.  
  
-   Переносимость.  
  
## Заголовок Pimpl  
  
```cpp  
  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 Эта pimpl избежать каскадов перестроения и хрупких макетов объекта.  Он хорошо подходит для \(\) является транзитивным популярных типов.  
  
## Реализация Pimpl  
 Определите класс `impl` в cpp\-файле.  
  
```cpp  
  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## Рекомендации  
 Возможно, добавление поддержки не функцию специализации обмена.  
  
## См. также  
 [Возвращение к C\+\+](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [Справочник по языку C\+\+](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md)