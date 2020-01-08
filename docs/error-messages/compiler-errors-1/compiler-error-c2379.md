---
title: Ошибка компилятора C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: f096791a6120023e079b93452a4b35c669db2139
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302111"
---
# <a name="compiler-error-c2379"></a>Ошибка компилятора C2379

номер формального параметра имеет другой тип при повышении уровня

Тип указанного параметра несовместим с использованием специальных предложений по умолчанию с типом в предыдущем объявлении. Это ошибка в ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) и предупреждение с расширениями Майкрософт ( **/Ze**).

Следующий пример приводит к возникновению ошибки C2379:

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
