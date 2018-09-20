---
title: Объявление индекса свойства | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6917742b285b3700548b54fef164d01c0594e5e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380469"
---
# <a name="property-index-declaration"></a>Объявление индекса свойства

Синтаксис объявления индексированное свойство было изменено с управляемых расширений для C++ в Visual C++.

Два основной недостаток поддержки управляемых расширений языка индексированных свойств является невозможность предоставления индексация уровня класса; то есть все индексированные свойства являются обязательными для следует присвоить ему имя, и таким образом не существует способа, например, для предоставления управляемого подстрочный оператор, который можно применить непосредственно к `Vector` или `Matrix` объекта класса. Второй, менее критичный недостаток — что визуально трудно отличить свойство от индексированное свойство — количество параметров является единственным указанием. Наконец индексированные свойства подвержены тем же проблемам, что неиндексированных свойств - методы доступа не обрабатываются как атомарные единицы, а разделяются на отдельные методы.  Пример:

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

Как вы видите здесь, индексаторов различаются только дополнительные параметры, чтобы указать два или отдельные индекса измерения. В новом синтаксисе индексаторов различаются по квадратная скобка ([],) после имени индексатора и указывают его номер и тип каждого индекса:

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

Чтобы указать индексатор на уровне класса, могут применяться непосредственно к объектам класса в новом синтаксисе `default` повторно используется ключевое слово для замены явно заданного имени. Пример:

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

В новом синтаксисе при индексации по умолчанию указано свойство, зарезервированы два следующие имена: `get_Item` и `set_Item`. Это обусловлено базовые имена, созданные для индексированного свойства по умолчанию.

Обратите внимание на то, что не существует простого индекса синтаксис Аналогично синтаксису простого свойства.

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
