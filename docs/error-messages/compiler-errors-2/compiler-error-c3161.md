---
title: Ошибка компилятора C3161 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11396ccad33489b41d18759ba4d2f00b445e94a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136079"
---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161

«интерфейс»: вложенный класс, структура, объединение или интерфейс в интерфейсе является недопустимым; недопустимо вложение интерфейса в класс, структуру или объединение

[__Interface](../../cpp/interface.md) может присутствовать только в глобальной области или в пространстве имен. Класс, структура или объединение не может использоваться в интерфейсе.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3161.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```