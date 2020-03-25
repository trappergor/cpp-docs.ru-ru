---
title: Предупреждение компилятора (уровень 1) C4616
ms.date: 11/04/2016
f1_keywords:
- C4616
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
ms.openlocfilehash: fd36d0cdbcaaeca4f84ce85aa80f3bb1fba616a0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185910"
---
# <a name="compiler-warning-level-1-c4616"></a>Предупреждение компилятора (уровень 1) C4616

предупреждение директивы pragma \#: номер предупреждения "число" не является допустимым предупреждением компилятора

Номер предупреждения, указанный в прагма pragma [warning](../../preprocessor/warning.md) , нельзя переназначить. Директива pragma была пропущена.

Следующий пример приводит к возникновению ошибки C4616:

```cpp
// C4616.cpp
// compile with: /W1 /c
#pragma warning( disable : 0 )   // C4616
#pragma warning( disable : 999 )   // OK
#pragma warning( disable : 4998 )   // OK
```
