---
title: Предупреждение компилятора (уровень 1) C4526 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed6f2da3252c27b7a84b4d5b73f7e8ba52823dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118509"
---
# <a name="compiler-warning-level-1-c4526"></a>Предупреждение компилятора (уровень 1) C4526

«функция»: статическая функция-член не может переопределить виртуальную функцию "виртуальный function'override игнорируются, виртуальная функция будет скрыта

Статическую функцию-член соответствует критериям для переопределения виртуальной функции, что делает функция-член как виртуальной, так и статические.

Следующий код вызывает ошибку C4526:

```
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

Ниже приведены возможные исправления.

- Если функция должна переопределить виртуальную функцию базового класса, удалите статический спецификатор.

- Если функция должна быть статической функцией-членом, переименуйте его, чтобы это не противоречит виртуальная функция базового класса.