---
title: Ошибка компилятора C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: d099c4a0f6e1ea77a25213e3873b8a0814e28dcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201999"
---
# <a name="compiler-error-c2821"></a>Ошибка компилятора C2821

первый формальный параметр для "operator new" должен иметь тип "unsigned int"

Первым формальным параметром [оператора New](../../standard-library/new-operators.md#op_new) должен быть неподписанный `int`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2821:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
