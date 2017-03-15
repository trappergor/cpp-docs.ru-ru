---
title: "Перегруженные операторы | Microsoft Docs"
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
  - "перегрузка операторов, в классе CLR"
  - "операторы [C++], перегрузка"
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Перегруженные операторы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

По сравнению с управляемыми расширениями для C\+\+, в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] существенно изменился порядок перегрузки операторов.  
  
 Например, в объявлении ссылочного типа вместо синтаксиса неуправляемого кода `operator+` использовалась явная запись базового внутреннего имени оператора \(в этом случае — `op_Addition`\).  Кроме того, вызов оператора осуществлялся явным образом с использованием его имени, в связи с чем не были реализованы два основных преимущества перегрузки операторов: интуитивно понятный синтаксис и возможность использования новых типов совместно с существующими.  Примеры.  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 В новом синтаксисе объявление и использование статических операторов осуществляется способом, знакомым программисту по работе с неуправляемым кодом C\+\+.  Ниже приведен пример класса `Vector`, реализованного с использованием нового синтаксиса:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)