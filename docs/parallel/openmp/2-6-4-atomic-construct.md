---
title: "2.6.4 Конструкция atomic | Microsoft Docs"
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
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.4 Конструкция atomic
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `atomic` Директива обеспечивает атомарным образом, обновление конкретное расположение в памяти вместо предоставлением доступа к тому несколько одновременных потоков записи. Синтаксис `atomic` директивы таков:  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 Оператор выражения должен иметь одно из следующих форм:  
  
 *x binop*= *expr*  
  
 x ++  
  
 ++ x  
  
 x--  
  
 --x  
  
 В предыдущем выражении:  
  
-   *x* lvalue выражение с скалярный тип.  
  
-   *expr* выражение с скалярного типа, и он не ссылается на объекте, обозначенном *x*.  
  
-   `binop` не перегруженного оператора и является одним из +, *, -, / &, ^, &#124; <\<, или >>.  
  
 Несмотря на то, что он определяется реализацией ли реализация заменяет все `atomic` директивы с **критические** директивы с одинаковым уникальным *имя*,  `atomic` директива позволяет лучше оптимизации. Часто аппаратные инструкции доступны, можно выполнять атомарные обновления с наименьшей нагрузки.  
  
 Только нагрузки и хранилище объекте, обозначенном *x* являются атомарными; вычисления *expr* не является атомарным. Чтобы избежать конкуренции, следует защитить все обновления расположения параллельно `atomic` директив, кроме тех, которые называются бесплатно конкуренции.  
  
 Ограничения для `atomic` директива таковы:  
  
-   Все atomic ссылки на место хранения x в программе должны иметь совместимый тип.  
  
## <a name="examples"></a>Примеры  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```