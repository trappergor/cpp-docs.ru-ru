---
title: "Объявление индекса свойства | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fbd1158dce82b2cc2ae7d15e7b66d6b9058d8c85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="property-index-declaration"></a>Объявление индекса свойства
Синтаксис объявления индексированного свойства отличается от управляемых расширений для C++ к Visual C++.  
  
 Два основной недостаток поддержки языка управляемых расширений индексированных свойств — это невозможность предоставления индексация уровня класса; то есть все индексированные свойства должны задать имя, и таким образом нет возможности, например, для обеспечения управляемого подстрочный оператор, который может применяться непосредственно к `Vector` или `Matrix` объекта класса. Второй, менее критичный недостаток — что он сложность визуального различения свойства Индексированное свойство - число параметров является единственным указанием. Наконец индексированные свойства подвержены тем же проблемам те неиндексированных свойств - методы доступа не рассматриваются как единый модуль, а разделяются на отдельные методы.  Пример:  
  
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
  
 Как здесь можно увидеть, индексаторов различаются только по дополнительным параметрам, указывающим одно или отдельные индекс измерения. В новом синтаксисе индексаторов различаются по выражение в квадратных скобках ([],) после имени индексатора и указав, число и тип каждого индекса:  
  
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
  
 Для указания уровня индексатора класса, который может применяться непосредственно к объектам этого класса в новом синтаксисе `default` ключевое слово используется повторно вместо явно заданного имени. Пример:  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
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
  
 В новом синтаксисе при индексации по умолчанию свойство указано, зарезервированы две следующие имена: `get_Item` и `set_Item`. Это, так как эти основные имена, создаваемые для индексированного свойства по умолчанию.  
  
 Обратите внимание, что нет простого синтаксиса индексов аналогичен синтаксис простого свойства.  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 