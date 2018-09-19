---
title: Ошибка компилятора C3848 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3848
dev_langs:
- C++
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81af73813f1f9c6c388ec6946ef9131cad413747
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069590"
---
# <a name="compiler-error-c3848"></a>Ошибка компилятора C3848

выражение, имеющее тип «тип» потеряет некоторые квалификаторы const или volatile вызове «функции»

Переменная с указанным типом const или volatile может вызывать только член функции, определенные с помощью одной или более поздней версии const и volatile.

Следующий пример приводит к возникновению ошибки C3848:

```
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```