---
title: 2.6.4 конструкция atomic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66f0dc8469d1d70b2697df1fe120f10142d90dbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688132"
---
# <a name="264-atomic-construct"></a>2.6.4 Конструкция atomic
`atomic` Директива гарантирует, что конкретное расположение в памяти обновлены атомарным образом, а не предоставляя его возможности несколько одновременных потоков записи. Синтаксис `atomic` директивы таков:  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 Оператор выражения должен иметь одно из следующих форм:  
  
 *x binop*= *expr*  
  
 x ++  
  
 ++ x  
  
 x--  
  
 --x  
  
 В предыдущем выражения:  
  
-   *x* выражение lvalue, скалярный тип.  
  
-   *expr* является выражением с скалярного типа, и он не ссылается на объекте, обозначенном *x*.  
  
-   `binop` не является перегруженного оператора и является одним из +, *, -, / &, ^, &#124;, <\<, или >>.  
  
 Несмотря на то, что он определяется реализацией ли реализация заменяет все `atomic` директив с **критические** директив с одинаковым уникальным *имя*, `atomic` директивы Разрешает улучшенной оптимизации. Часто инструкции оборудования доступны, можно выполнить обновление atomic с наименее затратен.  
  
 Только нагрузки и хранилище объекте, обозначенном *x* являются атомарными; оценки *expr* не является атомарной. Чтобы избежать конкуренции, все обновления расположения в параллельном режиме должны быть защищены с `atomic` директив, кроме тех, которые были определены как бесплатно гонки.  
  
 Ограничения для `atomic` директивы, следующим образом:  
  
-   Все atomic ссылки на расположение хранилища x в программе должен быть в совместимый тип.  
  
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