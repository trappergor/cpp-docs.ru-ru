---
title: Ошибка компилятора C2814 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2814
dev_langs:
- C++
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef85e143b13ea5184235676179e33b387f751aa8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046580"
---
# <a name="compiler-error-c2814"></a>Ошибка компилятора C2814

member: неуправляемый тип не может быть вложенным в управляемом типе или типе WinRT "type"

## <a name="example"></a>Пример

Неуправляемый тип не может быть вложенным в типе CLR или WinRT. В следующем примере показано возникновение ошибки C2814 и приводятся сведения по ее устранению.

```
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```
