---
title: "Объявление индекса свойства | Microsoft Docs"
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
  - "индексаторы по умолчанию"
  - "по умолчанию, индексаторы"
  - "индексированные свойства, C++"
  - "индексаторы"
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Объявление индекса свойства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] синтаксис объявления индексированного свойства изменился по сравнению с управляемыми расширениями для C\+\+.  
  
 Первый из двух главных недостатков поддержки индексированных свойств языком управляемых расширений заключается в невозможности обеспечить нижнюю индексацию на уровне класса; иными словами, всем индексируемым свойствам необходимо присваивать имена. Таким образом, становится невозможно, например, предоставить управляемый оператор нижней индексации, который можно напрямую применить к объекту класса `Vector` или `Matrix`.  Второй, менее критичный недостаток, — это сложность визуального различения свойства и индексированного свойства. Единственным показателем здесь выступает количество параметров.  И наконец, индексированные свойства подвержены тем же проблемам, что и обычные: методы доступа не обрабатываются как неделимые единицы, а разделяются на отдельные методы.  Примеры.  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 Как здесь хорошо видно, индексаторы можно различить только по дополнительным параметрам, указывающим одно\- или двухмерный индекс.  В новом синтаксисе эти индексы различаются по скобкам \(\[,\]\), которые следуют за именем индексатора и указывают его номер и тип.  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 В новом синтаксисе вместо явно заданного имени повторно используется ключевое слово `default`, которое позволяет обозначить индексатор на уровне класса, применимый непосредственно к объектам этого класса в новом синтаксисе.  Примеры.  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat …  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer …  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 В новом синтаксисе при указании индексированного свойства по умолчанию резервируются два следующих имени: `get_Item` и `set_Item`.  Это основные имена, создаваемые для индексированного свойства по умолчанию.  
  
 Обратите внимание, что простого синтаксиса индексов, аналогичного простому синтаксису свойств, не существует.  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Практическое руководство. Использование индексированных свойств](../misc/how-to-use-indexed-properties.md)