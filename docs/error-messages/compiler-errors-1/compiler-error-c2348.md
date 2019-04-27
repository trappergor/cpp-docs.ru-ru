---
title: Ошибка компилятора C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 379bcc7f37ff8942e4e45c6a6188438400937875
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187910"
---
# <a name="compiler-error-c2348"></a>Ошибка компилятора C2348

«имя_типа»: не является агрегированным в стиле C, невозможно экспортировать во внедренный IDL

Чтобы поместить `struct` в IDL-файл с [Экспорт](../../windows/export.md) атрибут, `struct` должен содержать только данные.

Следующий пример приводит к возникновению ошибки C2348:

```
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```