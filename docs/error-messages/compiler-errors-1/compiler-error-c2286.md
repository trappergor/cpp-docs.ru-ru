---
title: Ошибка компилятора C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 7d3b8297c5f5da29b99abe78999396e8c44df0fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182773"
---
# <a name="compiler-error-c2286"></a>Ошибка компилятора C2286

указатели на члены «идентификатор» представления уже установлен в значение «наследование» - объявление проигнорировано

Существует два различных представления указателей на члены класса.

Дополнительные сведения см. в разделе [ключевые слова наследования](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C2286:

```
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```