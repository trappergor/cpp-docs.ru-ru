---
title: 2.6.4 конструкция atomic | Документация Майкрософт
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
ms.openlocfilehash: f92e0b0c881ec1f8d54adce4a12f58ad514ed8f5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437486"
---
# <a name="264-atomic-construct"></a>2.6.4 Конструкция atomic

`atomic` Директива гарантирует, что конкретное расположение в памяти обновляется атомарно, вместо того чтобы предоставлять к нему доступ можно несколько одновременных потоков записи. Синтаксис `atomic` директива выглядит следующим образом:

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

- *x* выражение lvalue, скалярный тип.

- *expr* выражение с скалярный тип, и он не ссылается на объект, указанный *x*.

- `binop` не является перегруженного оператора и является одним из +, \*, -, / &, ^, &#124;, <\<, или >>.

Несмотря на то, что он определяется реализацией ли реализация заменяет все `atomic` директивы с **критических** директивы, которые имеют одинаковый уникальный *имя*, `atomic` директива Разрешает улучшенный оптимизации. Часто оборудование инструкции можно найти, можно выполнять атомарные обновления с наименее затратен.

Только нагрузки и хранилище, назначенному с помощью объекта *x* неделимы; вычисления *expr* не является атомарной. Чтобы избежать состояний гонки, все обновления расположения в параллельном режиме должны быть защищены с помощью `atomic` директив, кроме тех, которые известны свободную от условия конкуренции.

Ограничения для `atomic` директива таковы:

- Все atomic ссылки на расположение хранилища x в программе должен быть в совместимый тип.

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